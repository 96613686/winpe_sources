# StateRepository::Cache::Entity::Package_NoThrow::GetAreMrtResourcesRedirected(void)

- ea: `0x18001a6d4`
- end: `0x18001a742`
- name: `?GetAreMrtResourcesRedirected@Package_NoThrow@Entity@Cache@StateRepository@@QEBA_NXZ`
- size: `110`
- prototype: `bool __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018748`

## callees

- `0x18001a6d4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a735`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a735`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001a701`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001a701`

## pseudocode

```c
char __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetAreMrtResourcesRedirected(LPCWCH *this)
{
  char v2; // bl
  int v4; // [rsp+40h] [rbp+8h] BYREF

  v2 = 1;
  if ( (*((_DWORD *)this + 7) & 0x800) == 0 )
  {
    v4 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v4, 0);
    if ( v4 != 5 || CompareStringOrdinal(this[7], 2, L"C:", 2, 1) == 2 )
      return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18001a6d4  mov     [rsp+arg_8], rbx
0x18001a6d9  push    rdi
0x18001a6da  sub     rsp, 30h
0x18001a6de  test    dword ptr [rcx+1Ch], 800h
0x18001a6e5  mov     rdi, rcx
0x18001a6e8  mov     ebx, 1
0x18001a6ed  jnz     short loc_18001A710
0x18001a6ef  xor     r8d, r8d
0x18001a6f2  mov     [rsp+38h+arg_0], 0
0x18001a6fa  lea     rdx, [rsp+38h+arg_0]
0x18001a6ff  xor     ecx, ecx
0x18001a701  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001a707  cmp     [rsp+38h+arg_0], 5
0x18001a70c  jz      short loc_18001A71D
0x18001a70e  xor     bl, bl
0x18001a710  mov     al, bl
0x18001a712  mov     rbx, [rsp+38h+arg_8]
0x18001a717  add     rsp, 30h
0x18001a71b  pop     rdi
0x18001a71c  retn
0x18001a71d  mov     rcx, [rdi+38h]; lpString1
0x18001a721  lea     r8, aC; "C:"
0x18001a728  mov     r9d, 2; cchCount2
0x18001a72e  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x18001a732  mov     edx, r9d; cchCount1
0x18001a735  call    cs:__imp_CompareStringOrdinal
0x18001a73b  cmp     eax, 2
0x18001a73e  jnz     short loc_18001A710
0x18001a740  jmp     short loc_18001A70E
```
