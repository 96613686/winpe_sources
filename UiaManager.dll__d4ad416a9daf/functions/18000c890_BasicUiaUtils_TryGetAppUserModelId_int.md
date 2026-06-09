# BasicUiaUtils::TryGetAppUserModelId(int)

- ea: `0x18000c890`
- end: `0x18000c977`
- name: `?TryGetAppUserModelId@BasicUiaUtils@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180066550`
- `0x18006ef3c`

## callees

- `0x18000c890`
- `0x18000c980`
- `0x180010f78`
- `0x180026734`
- `0x180043680`
- `0x1800441ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c94d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c94d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18000c8f9`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18000c8f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BasicUiaUtils::TryGetAppUserModelId(__int64 a1, DWORD a2)
{
  char *v3; // rbx
  UINT32 applicationUserModelIdLength; // [rsp+20h] [rbp-148h] BYREF
  char *v6; // [rsp+28h] [rbp-140h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+40h] [rbp-128h] BYREF

  v3 = (char *)OpenProcessTokenHelper(a1, a2, a2);
  v6 = v3;
  if ( ((unsigned __int64)(v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    || (memset_0(applicationUserModelId, 0, 0x104u),
        applicationUserModelIdLength = 130,
        GetApplicationUserModelIdFromToken(v3, &applicationUserModelIdLength, applicationUserModelId)) )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 7;
    *(_WORD *)a1 = 0;
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v3);
  }
  else
  {
    std::wstring::wstring(a1, applicationUserModelId, applicationUserModelIdLength - 1);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v6);
  }
  return a1;
}

```

## disassembly

```asm
0x18000c890  mov     [rsp+arg_10], rbx
0x18000c895  push    rdi
0x18000c896  sub     rsp, 160h
0x18000c89d  mov     rax, cs:__security_cookie
0x18000c8a4  xor     rax, rsp
0x18000c8a7  mov     [rsp+168h+var_18], rax
0x18000c8af  mov     rdi, rcx
0x18000c8b2  mov     [rsp+168h+var_140], rcx
0x18000c8b7  mov     r8d, edx; unsigned int
0x18000c8ba  call    ?OpenProcessTokenHelper@@YAPEAXKHK@Z; OpenProcessTokenHelper(ulong,int,ulong)
0x18000c8bf  mov     rbx, rax
0x18000c8c2  mov     [rsp+168h+var_140], rax
0x18000c8c7  inc     rax
0x18000c8ca  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000c8d0  jz      short loc_18000C925
0x18000c8d2  xor     edx, edx; Val
0x18000c8d4  mov     r8d, 104h; Size
0x18000c8da  lea     rcx, [rsp+168h+applicationUserModelId]; void *
0x18000c8df  call    memset_0
0x18000c8e4  mov     [rsp+168h+applicationUserModelIdLength], 82h
0x18000c8ec  lea     r8, [rsp+168h+applicationUserModelId]; applicationUserModelId
0x18000c8f1  lea     rdx, [rsp+168h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18000c8f6  mov     rcx, rbx; token
0x18000c8f9  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18000c8ff  test    eax, eax
0x18000c901  jnz     short loc_18000C925
0x18000c903  mov     r8d, [rsp+168h+applicationUserModelIdLength]
0x18000c908  dec     r8d
0x18000c90b  lea     rdx, [rsp+168h+applicationUserModelId]
0x18000c910  mov     rcx, rdi
0x18000c913  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18000c918  nop
0x18000c919  lea     rcx, [rsp+168h+var_140]
0x18000c91e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000c923  jmp     short loc_18000C953
0x18000c925  xorps   xmm0, xmm0
0x18000c928  movups  xmmword ptr [rdi], xmm0
0x18000c92b  mov     qword ptr [rdi+10h], 0
0x18000c933  mov     qword ptr [rdi+18h], 7
0x18000c93b  xor     eax, eax
0x18000c93d  mov     [rdi], ax
0x18000c940  lea     rax, [rbx-1]
0x18000c944  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c948  ja      short loc_18000C953
0x18000c94a  mov     rcx, rbx; hObject
0x18000c94d  call    cs:__imp_CloseHandle
0x18000c953  mov     rax, rdi
0x18000c956  mov     rcx, [rsp+168h+var_18]
0x18000c95e  xor     rcx, rsp; StackCookie
0x18000c961  call    __security_check_cookie
0x18000c966  mov     rbx, [rsp+168h+arg_10]
0x18000c96e  add     rsp, 160h
0x18000c975  pop     rdi
0x18000c976  retn
```
