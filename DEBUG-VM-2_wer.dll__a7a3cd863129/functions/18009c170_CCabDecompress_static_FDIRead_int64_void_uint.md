# CCabDecompress::static_FDIRead(__int64,void *,uint)

- ea: `0x18009c170`
- end: `0x18009c26d`
- name: `?static_FDIRead@CCabDecompress@@KAI_JPEAXI@Z`
- size: `253`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001fe24`
- `0x18009c170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c1f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c1f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c1af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c1af`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009c1d5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009c1d5`

## pseudocode

```c
__int64 __fastcall CCabDecompress::static_FDIRead(INT_PTR hf, void *pv, UINT cb)
{
  HANDLE *v6; // rcx
  DWORD LastError; // eax
  unsigned int v8; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  if ( hf && pv )
  {
    v6 = *(HANDLE **)hf;
    if ( !v6 || WaitForSingleObject(*v6, 0) )
    {
      if ( ReadFile(*(HANDLE *)(hf + 8), pv, cb, &NumberOfBytesRead, 0) )
        return NumberOfBytesRead;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids, v8);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18009c170  mov     [rsp+arg_8], rbx
0x18009c175  mov     [rsp+arg_10], rsi
0x18009c17a  push    rdi
0x18009c17b  sub     rsp, 30h
0x18009c17f  mov     [rsp+38h+NumberOfBytesRead], 0
0x18009c187  mov     esi, r8d
0x18009c18a  mov     rdi, rdx
0x18009c18d  mov     rbx, rcx
0x18009c190  test    rcx, rcx
0x18009c193  jz      loc_18009C22C
0x18009c199  test    rdx, rdx
0x18009c19c  jz      loc_18009C22C
0x18009c1a2  mov     rcx, [rcx]
0x18009c1a5  test    rcx, rcx
0x18009c1a8  jz      short loc_18009C1BD
0x18009c1aa  mov     rcx, [rcx]; hHandle
0x18009c1ad  xor     edx, edx; dwMilliseconds
0x18009c1af  call    cs:__imp_WaitForSingleObject
0x18009c1b5  test    eax, eax
0x18009c1b7  jz      loc_18009C25A
0x18009c1bd  mov     rcx, [rbx+8]; hFile
0x18009c1c1  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009c1c6  mov     r8d, esi; nNumberOfBytesToRead
0x18009c1c9  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18009c1d2  mov     rdx, rdi; lpBuffer
0x18009c1d5  call    cs:__imp_ReadFile
0x18009c1db  test    eax, eax
0x18009c1dd  jnz     short loc_18009C226
0x18009c1df  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c1e6  lea     rax, WPP_GLOBAL_Control
0x18009c1ed  cmp     rcx, rax
0x18009c1f0  jz      short loc_18009C25A
0x18009c1f2  test    byte ptr [rcx+1Ch], 1
0x18009c1f6  jz      short loc_18009C25A
0x18009c1f8  call    cs:__imp_GetLastError
0x18009c1fe  mov     ecx, eax; unsigned int
0x18009c200  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009c205  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c20c  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009c213  mov     edx, 3Ah ; ':'
0x18009c218  mov     r9d, eax
0x18009c21b  mov     rcx, [rcx+10h]
0x18009c21f  call    WPP_SF_d
0x18009c224  jmp     short loc_18009C25A
0x18009c226  mov     eax, [rsp+38h+NumberOfBytesRead]
0x18009c22a  jmp     short loc_18009C25D
0x18009c22c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c233  lea     rax, WPP_GLOBAL_Control
0x18009c23a  cmp     rcx, rax
0x18009c23d  jz      short loc_18009C25A
0x18009c23f  test    byte ptr [rcx+1Ch], 1
0x18009c243  jz      short loc_18009C25A
0x18009c245  mov     rcx, [rcx+10h]
0x18009c249  lea     r8, WPP_79ef5c27a1f136def879418ea58f312b_Traceguids
0x18009c250  mov     edx, 39h ; '9'
0x18009c255  call    WPP_SF_
0x18009c25a  or      eax, 0FFFFFFFFh
0x18009c25d  mov     rbx, [rsp+38h+arg_8]
0x18009c262  mov     rsi, [rsp+38h+arg_10]
0x18009c267  add     rsp, 30h
0x18009c26b  pop     rdi
0x18009c26c  retn
```
