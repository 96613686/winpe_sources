# RaDestroySid

- ea: `0x180003e30`
- end: `0x180003f48`
- name: `RaDestroySid`
- size: `280`
- prototype: `void __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180003e30`
- `0x180004cb0`
- `0x18000b774`
- `0x18000b800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e5c`

## string_xrefs

- `0x180003eb5`: `RaDestroySid`
- `0x180003f04`: `RaDestroySid`
- `0x180003f2a`: `RaDestroySid`

## pseudocode

```c
void __fastcall RaDestroySid(LPVOID lpMem)
{
  HANDLE ProcessHeap; // rdi
  int v3; // r8d
  DWORD LastError; // eax
  int v5; // r8d
  DWORD v6; // eax
  int v7; // r8d

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap || (v6 = GetLastError()) == 0 )
    {
      if ( HeapFree(ProcessHeap, 0, lpMem) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_sdq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)&WPP_GLOBAL_Control,
            v3,
            (unsigned int)"RaDestroySid",
            157,
            (char)lpMem);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_sdqd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            v5,
            (unsigned int)"RaDestroySid",
            157,
            (char)lpMem,
            LastError);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v7, (unsigned int)"RaDestroySid", 157, v6);
    }
  }
}

```

## disassembly

```asm
0x180003e30  test    rcx, rcx
0x180003e33  jz      short locret_180003E8D
0x180003e35  push    rbx
0x180003e36  sub     rsp, 40h
0x180003e3a  mov     rbx, rcx
0x180003e3d  mov     [rsp+48h+arg_0], rdi
0x180003e42  call    cs:__imp_GetProcessHeap
0x180003e48  mov     rdi, rax
0x180003e4b  test    rax, rax
0x180003e4e  jz      loc_180003ED9
0x180003e54  mov     r8, rbx; lpMem
0x180003e57  xor     edx, edx; dwFlags
0x180003e59  mov     rcx, rdi; hHeap
0x180003e5c  call    cs:__imp_HeapFree
0x180003e62  test    eax, eax
0x180003e64  jz      short loc_180003E8E
0x180003e66  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e6d  lea     rdx, WPP_GLOBAL_Control
0x180003e74  cmp     rcx, rdx
0x180003e77  jz      short loc_180003E83
0x180003e79  test    byte ptr [rcx+1Ch], 2
0x180003e7d  jnz     loc_180003F26
0x180003e83  mov     rdi, [rsp+48h+arg_0]
0x180003e88  add     rsp, 40h
0x180003e8c  pop     rbx
0x180003e8d  retn
0x180003e8e  call    cs:__imp_GetLastError
0x180003e94  test    eax, eax
0x180003e96  jz      short loc_180003E83
0x180003e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e9f  lea     rdx, WPP_GLOBAL_Control
0x180003ea6  cmp     rcx, rdx
0x180003ea9  jz      short loc_180003E83
0x180003eab  test    byte ptr [rcx+1Ch], 4
0x180003eaf  jz      short loc_180003E83
0x180003eb1  mov     rcx, [rcx+10h]
0x180003eb5  lea     r9, aRadestroysid_0; "RaDestroySid"
0x180003ebc  mov     [rsp+48h+var_18], eax
0x180003ec0  mov     edx, 0Fh
0x180003ec5  mov     [rsp+48h+var_20], rbx
0x180003eca  mov     [rsp+48h+var_28], 9Dh
0x180003ed2  call    WPP_SF_sdqd
0x180003ed7  jmp     short loc_180003E83
0x180003ed9  call    cs:__imp_GetLastError
0x180003edf  test    eax, eax
0x180003ee1  jz      loc_180003E54
0x180003ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eee  lea     rdx, WPP_GLOBAL_Control
0x180003ef5  cmp     rcx, rdx
0x180003ef8  jz      short loc_180003E83
0x180003efa  test    byte ptr [rcx+1Ch], 4
0x180003efe  jz      short loc_180003E83
0x180003f00  mov     rcx, [rcx+10h]
0x180003f04  lea     r9, aRadestroysid_0; "RaDestroySid"
0x180003f0b  mov     dword ptr [rsp+48h+var_20], eax
0x180003f0f  mov     edx, 0Dh
0x180003f14  mov     [rsp+48h+var_28], 9Dh
0x180003f1c  call    WPP_SF_sdd
0x180003f21  jmp     loc_180003E83
0x180003f26  mov     rcx, [rcx+10h]
0x180003f2a  lea     r9, aRadestroysid_0; "RaDestroySid"
0x180003f31  mov     [rsp+48h+var_20], rbx
0x180003f36  mov     [rsp+48h+var_28], 9Dh
0x180003f3e  call    WPP_SF_sdq
0x180003f43  jmp     loc_180003E83
```
