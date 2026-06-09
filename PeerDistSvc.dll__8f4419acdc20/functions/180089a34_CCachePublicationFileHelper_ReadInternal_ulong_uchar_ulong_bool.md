# CCachePublicationFileHelper::ReadInternal(ulong,uchar *,ulong *,bool)

- ea: `0x180089a34`
- end: `0x180089be7`
- name: `?ReadInternal@CCachePublicationFileHelper@@AEAAKKPEAEPEAK_N@Z`
- size: `435`
- prototype: `unsigned int(CCachePublicationFileHelper *__hidden this, unsigned int, unsigned __int8 *, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180088c30`
- `0x180089340`

## callees

- `0x180008290`
- `0x18002a8bc`
- `0x180089a34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089b12`
- `KERNEL32!ReadFile` at `0x180089a8e`
- `KERNEL32!ReadFile` at `0x180089a8e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180089b08`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180089b08`

## pseudocode

```c
__int64 __fastcall CCachePublicationFileHelper::ReadInternal(
        CCachePublicationFileHelper *this,
        DWORD a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        bool a5)
{
  struct _OVERLAPPED *lpOverlapped; // rbp
  void *v10; // rcx
  DWORD LastError; // eax
  unsigned int v12; // ebx
  CHostedCacheMsgEncoding *v13; // rcx
  __int64 v14; // rdx
  DWORD v15; // r9d
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+8h] BYREF

  lpOverlapped = (struct _OVERLAPPED *)((char *)this + 32);
  *((_QWORD *)this + 7) = *((_QWORD *)this + 10);
  *((_DWORD *)this + 12) = *((_DWORD *)this + 16);
  *((_DWORD *)this + 13) = *((_DWORD *)this + 17);
  *a4 = 0;
  v10 = (void *)*((_QWORD *)this + 3);
  NumberOfBytesTransferred = 0;
  if ( ReadFile(v10, a3, a2, 0, lpOverlapped) || (LastError = GetLastError(), v12 = LastError, LastError == 997) )
  {
    if ( GetOverlappedResult(*((HANDLE *)this + 3), lpOverlapped, &NumberOfBytesTransferred, 1) )
    {
      v15 = NumberOfBytesTransferred;
      if ( NumberOfBytesTransferred > a2 || !a5 && NumberOfBytesTransferred < a2 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            130,
            WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids,
            NumberOfBytesTransferred);
          v13 = WPP_GLOBAL_Control;
        }
        v12 = 774;
        goto LABEL_23;
      }
      *((_QWORD *)this + 8) += NumberOfBytesTransferred;
      v12 = 0;
      *a4 = v15;
      goto LABEL_8;
    }
    LastError = GetLastError();
    v12 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      return v12;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      goto LABEL_23;
    v14 = 129;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v13 + 12), v14, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, LastError);
LABEL_8:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v14 = 128;
    goto LABEL_7;
  }
LABEL_23:
  if ( v13 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v13 + 108) & 4) != 0
    && *((_BYTE *)v13 + 105) >= 4u )
  {
    WPP_SF_qDD(*((_QWORD *)v13 + 12), 131, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, a3, *a4, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180089a34  mov     [rsp+arg_8], rbx
0x180089a39  mov     [rsp+arg_10], rbp
0x180089a3e  push    rsi
0x180089a3f  push    rdi
0x180089a40  push    r13
0x180089a42  push    r14
0x180089a44  push    r15
0x180089a46  sub     rsp, 30h
0x180089a4a  mov     rax, [rcx+50h]
0x180089a4e  lea     rbp, [rcx+20h]
0x180089a52  mov     [rbp+18h], rax
0x180089a56  mov     r15, r8
0x180089a59  mov     eax, [rcx+40h]
0x180089a5c  mov     r14, r9
0x180089a5f  mov     [rcx+30h], eax
0x180089a62  mov     esi, edx
0x180089a64  mov     eax, [rcx+44h]
0x180089a67  mov     rdi, rcx
0x180089a6a  mov     [rcx+34h], eax
0x180089a6d  mov     r8d, edx; nNumberOfBytesToRead
0x180089a70  mov     dword ptr [r9], 0
0x180089a77  mov     rdx, r15; lpBuffer
0x180089a7a  mov     rcx, [rcx+18h]; hFile
0x180089a7e  xor     r9d, r9d; lpNumberOfBytesRead
0x180089a81  mov     [rsp+58h+NumberOfBytesTransferred], 0
0x180089a89  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x180089a8e  call    cs:__imp_ReadFile
0x180089a94  lea     r13, WPP_GLOBAL_Control
0x180089a9b  test    eax, eax
0x180089a9d  jnz     short loc_180089AF6
0x180089a9f  call    cs:__imp_GetLastError
0x180089aa5  mov     ebx, eax
0x180089aa7  cmp     eax, 3E5h
0x180089aac  jz      short loc_180089AF6
0x180089aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180089ab5  cmp     rcx, r13
0x180089ab8  jz      loc_180089BCE
0x180089abe  test    byte ptr [rcx+6Ch], 4
0x180089ac2  jz      loc_180089B9A
0x180089ac8  cmp     byte ptr [rcx+69h], 1
0x180089acc  jb      loc_180089B9A
0x180089ad2  mov     edx, 80h
0x180089ad7  mov     rcx, [rcx+60h]
0x180089adb  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180089ae2  mov     r9d, eax
0x180089ae5  call    WPP_SF_d
0x180089aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180089af1  jmp     loc_180089B9A
0x180089af6  mov     rcx, [rdi+18h]; hFile
0x180089afa  lea     r8, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180089aff  mov     r9d, 1; bWait
0x180089b05  mov     rdx, rbp; lpOverlapped
0x180089b08  call    cs:__imp_GetOverlappedResult
0x180089b0e  test    eax, eax
0x180089b10  jnz     short loc_180089B3D
0x180089b12  call    cs:__imp_GetLastError
0x180089b18  mov     ebx, eax
0x180089b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180089b21  cmp     rcx, r13
0x180089b24  jz      loc_180089BCE
0x180089b2a  test    byte ptr [rcx+6Ch], 4
0x180089b2e  jz      short loc_180089B9A
0x180089b30  cmp     byte ptr [rcx+69h], 1
0x180089b34  jb      short loc_180089B9A
0x180089b36  mov     edx, 81h
0x180089b3b  jmp     short loc_180089AD7
0x180089b3d  mov     r9d, [rsp+58h+NumberOfBytesTransferred]
0x180089b42  cmp     r9d, esi
0x180089b45  ja      short loc_180089B61
0x180089b47  cmp     [rsp+58h+arg_20], 0
0x180089b4f  jnz     short loc_180089B56
0x180089b51  cmp     r9d, esi
0x180089b54  jb      short loc_180089B61
0x180089b56  add     [rdi+40h], r9
0x180089b5a  xor     ebx, ebx
0x180089b5c  mov     [r14], r9d
0x180089b5f  jmp     short loc_180089AEA
0x180089b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180089b68  cmp     rcx, r13
0x180089b6b  jz      short loc_180089B95
0x180089b6d  test    byte ptr [rcx+6Ch], 4
0x180089b71  jz      short loc_180089B95
0x180089b73  cmp     byte ptr [rcx+69h], 1
0x180089b77  jb      short loc_180089B95
0x180089b79  mov     rcx, [rcx+60h]
0x180089b7d  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180089b84  mov     edx, 82h
0x180089b89  call    WPP_SF_d
0x180089b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180089b95  mov     ebx, 306h
0x180089b9a  cmp     rcx, r13
0x180089b9d  jz      short loc_180089BCE
0x180089b9f  test    byte ptr [rcx+6Ch], 4
0x180089ba3  jz      short loc_180089BCE
0x180089ba5  cmp     byte ptr [rcx+69h], 4
0x180089ba9  jb      short loc_180089BCE
0x180089bab  mov     eax, [r14]
0x180089bae  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x180089bb5  mov     rcx, [rcx+60h]
0x180089bb9  mov     edx, 83h
0x180089bbe  mov     [rsp+58h+var_30], ebx
0x180089bc2  mov     r9, r15
0x180089bc5  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x180089bc9  call    WPP_SF_qDD
0x180089bce  mov     rbp, [rsp+58h+arg_10]
0x180089bd3  mov     eax, ebx
0x180089bd5  mov     rbx, [rsp+58h+arg_8]
0x180089bda  add     rsp, 30h
0x180089bde  pop     r15
0x180089be0  pop     r14
0x180089be2  pop     r13
0x180089be4  pop     rdi
0x180089be5  pop     rsi
0x180089be6  retn
```
