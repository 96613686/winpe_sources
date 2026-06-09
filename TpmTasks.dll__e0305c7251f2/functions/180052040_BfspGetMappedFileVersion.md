# BfspGetMappedFileVersion

- ea: `0x180052040`
- end: `0x180052143`
- name: `BfspGetMappedFileVersion`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180051ee4`
- `0x180051fa0`

## callees

- `0x1800078b0`
- `0x180052040`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005210c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005210c`
- `ntdll!LdrAccessResource` at `0x1800520dc`
- `ntdll!LdrAccessResource` at `0x1800520dc`
- `ntdll!LdrFindResource_U` at `0x1800520ac`
- `ntdll!LdrFindResource_U` at `0x1800520ac`

## pseudocode

```c
__int64 __fastcall BfspGetMappedFileVersion(__int64 a1)
{
  void *v1; // rbx
  ULONG Size; // [rsp+24h] [rbp-54h] BYREF
  PVOID Resource; // [rsp+28h] [rbp-50h] BYREF
  __int64 v5; // [rsp+30h] [rbp-48h]
  PIMAGE_RESOURCE_DATA_ENTRY ResourceDataEntry[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _LDR_RESOURCE_INFO v7; // [rsp+48h] [rbp-30h] BYREF

  v5 = 0;
  ResourceDataEntry[0] = 0;
  Size = 0;
  Resource = 0;
  v1 = (void *)(a1 | 1);
  ResourceDataEntry[1] = (PIMAGE_RESOURCE_DATA_ENTRY)(a1 | 1);
  v7.Type = 16;
  v7.Name = 1;
  v7.Language = 0;
  if ( LdrFindResource_U((PVOID)(a1 | 1), &v7, 3u, ResourceDataEntry) >= 0
    && LdrAccessResource(v1, ResourceDataEntry[0], &Resource, &Size) >= 0
    && Size >= 0x5C
    && !(unsigned int)_o__wcsicmp((char *)Resource + 6, L"VS_VERSION_INFO") )
  {
    HIDWORD(v5) = *((_DWORD *)Resource + 12);
    LODWORD(v5) = *((_DWORD *)Resource + 13);
  }
  return v5;
}

```

## disassembly

```asm
0x180052040  mov     r11, rsp
0x180052043  push    rbx
0x180052044  sub     rsp, 70h
0x180052048  mov     rax, cs:__security_cookie
0x18005204f  xor     rax, rsp
0x180052052  mov     [rsp+78h+var_18], rax
0x180052057  mov     rbx, rcx
0x18005205a  mov     qword ptr [r11-48h], 0
0x180052062  mov     qword ptr [r11-40h], 0
0x18005206a  mov     [rsp+78h+Size], 0
0x180052072  mov     qword ptr [r11-50h], 0
0x18005207a  or      rbx, 1
0x18005207e  mov     [rsp+78h+var_38], rbx
0x180052083  mov     qword ptr [r11-30h], 10h
0x18005208b  mov     qword ptr [r11-28h], 1
0x180052093  mov     qword ptr [r11-20h], 0
0x18005209b  lea     r9, [r11-40h]; ResourceDataEntry
0x18005209f  mov     r8d, 3; Level
0x1800520a5  lea     rdx, [r11-30h]; ResourceInfo
0x1800520a9  mov     rcx, rbx; BaseAddress
0x1800520ac  call    cs:__imp_LdrFindResource_U
0x1800520b2  mov     [rsp+78h+var_58], eax
0x1800520b6  jmp     short loc_1800520C6
0x1800520b8  mov     eax, 0C0000001h
0x1800520bd  mov     [rsp+78h+var_58], eax
0x1800520c1  mov     rbx, [rsp+78h+var_38]
0x1800520c6  test    eax, eax
0x1800520c8  js      short loc_18005212B
0x1800520ca  lea     r9, [rsp+78h+Size]; Size
0x1800520cf  lea     r8, [rsp+78h+Resource]; Resource
0x1800520d4  mov     rdx, [rsp+78h+ResourceDataEntry]; ResourceDataEntry
0x1800520d9  mov     rcx, rbx; BaseAddress
0x1800520dc  call    cs:__imp_LdrAccessResource
0x1800520e2  mov     [rsp+78h+var_58], eax
0x1800520e6  jmp     short loc_1800520F1
0x1800520e8  mov     eax, 0C0000001h
0x1800520ed  mov     [rsp+78h+var_58], eax
0x1800520f1  test    eax, eax
0x1800520f3  js      short loc_18005212B
0x1800520f5  cmp     [rsp+78h+Size], 5Ch ; '\'
0x1800520fa  jb      short loc_180052129
0x1800520fc  mov     rcx, [rsp+78h+Resource]
0x180052101  add     rcx, 6
0x180052105  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x18005210c  call    cs:__imp__o__wcsicmp
0x180052112  test    eax, eax
0x180052114  jnz     short loc_180052129
0x180052116  mov     rcx, [rsp+78h+Resource]
0x18005211b  mov     eax, [rcx+30h]
0x18005211e  mov     dword ptr [rsp+78h+var_48+4], eax
0x180052122  mov     eax, [rcx+34h]
0x180052125  mov     dword ptr [rsp+78h+var_48], eax
0x180052129  jmp     short $+2
0x18005212b  mov     rax, [rsp+78h+var_48]
0x180052130  mov     rcx, [rsp+78h+var_18]
0x180052135  xor     rcx, rsp; StackCookie
0x180052138  call    __security_check_cookie
0x18005213d  add     rsp, 70h
0x180052141  pop     rbx
0x180052142  retn
```
