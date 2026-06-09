# CCachePublicationFileHelper::WriteInternal(ulong,uchar *,ulong *)

- ea: `0x18008a8fc`
- end: `0x18008aa8d`
- name: `?WriteInternal@CCachePublicationFileHelper@@AEAAKKPEAEPEAK@Z`
- size: `401`
- prototype: `unsigned int(CCachePublicationFileHelper *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18008a370`
- `0x18008a680`

## callees

- `0x180008290`
- `0x18002a8bc`
- `0x18008a8fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9d3`
- `KERNEL32!WriteFile` at `0x18008a956`
- `KERNEL32!WriteFile` at `0x18008a956`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18008a9c9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18008a9c9`

## pseudocode

```c
__int64 __fastcall CCachePublicationFileHelper::WriteInternal(
        CCachePublicationFileHelper *this,
        DWORD a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  struct _OVERLAPPED *lpOverlapped; // rbp
  void *v9; // rcx
  DWORD LastError; // eax
  unsigned int v11; // ebx
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD v15; // ecx
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+8h] BYREF

  lpOverlapped = (struct _OVERLAPPED *)((char *)this + 32);
  *((_QWORD *)this + 7) = *((_QWORD *)this + 10);
  *((_DWORD *)this + 12) = *((_DWORD *)this + 16);
  *((_DWORD *)this + 13) = *((_DWORD *)this + 17);
  *a4 = 0;
  v9 = (void *)*((_QWORD *)this + 3);
  NumberOfBytesTransferred = 0;
  if ( WriteFile(v9, a3, a2, 0, lpOverlapped) || (LastError = GetLastError(), v11 = LastError, LastError == 997) )
  {
    if ( GetOverlappedResult(*((HANDLE *)this + 3), lpOverlapped, &NumberOfBytesTransferred, 1) )
    {
      v15 = NumberOfBytesTransferred;
      if ( NumberOfBytesTransferred == a2 )
      {
        *((_QWORD *)this + 8) += NumberOfBytesTransferred;
        v11 = 0;
        *a4 = v15;
        goto LABEL_20;
      }
      v11 = 774;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        return v11;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        goto LABEL_21;
      v13 = 109;
      v14 = 774;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v12 + 12), v13, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, v14);
LABEL_20:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    LastError = GetLastError();
    v11 = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      return v11;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      goto LABEL_21;
    v13 = 108;
LABEL_7:
    v14 = LastError;
    goto LABEL_8;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v13 = 107;
    goto LABEL_7;
  }
LABEL_21:
  if ( v12 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v12 + 108) & 4) != 0
    && *((_BYTE *)v12 + 105) >= 4u )
  {
    WPP_SF_qDD(*((_QWORD *)v12 + 12), 110, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids, a3, *a4, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x18008a8fc  mov     [rsp+arg_8], rbx
0x18008a901  mov     [rsp+arg_10], rbp
0x18008a906  push    rsi
0x18008a907  push    rdi
0x18008a908  push    r13
0x18008a90a  push    r14
0x18008a90c  push    r15
0x18008a90e  sub     rsp, 30h
0x18008a912  mov     rax, [rcx+50h]
0x18008a916  lea     rbp, [rcx+20h]
0x18008a91a  mov     [rbp+18h], rax
0x18008a91e  mov     r15, r8
0x18008a921  mov     eax, [rcx+40h]
0x18008a924  mov     r14, r9
0x18008a927  mov     [rcx+30h], eax
0x18008a92a  mov     esi, edx
0x18008a92c  mov     eax, [rcx+44h]
0x18008a92f  mov     rdi, rcx
0x18008a932  mov     [rcx+34h], eax
0x18008a935  mov     r8d, edx; nNumberOfBytesToWrite
0x18008a938  mov     dword ptr [r9], 0
0x18008a93f  mov     rdx, r15; lpBuffer
0x18008a942  mov     rcx, [rcx+18h]; hFile
0x18008a946  xor     r9d, r9d; lpNumberOfBytesWritten
0x18008a949  mov     [rsp+58h+NumberOfBytesTransferred], 0
0x18008a951  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x18008a956  call    cs:__imp_WriteFile
0x18008a95c  lea     r13, WPP_GLOBAL_Control
0x18008a963  test    eax, eax
0x18008a965  jnz     short loc_18008A9B7
0x18008a967  call    cs:__imp_GetLastError
0x18008a96d  mov     ebx, eax
0x18008a96f  cmp     eax, 3E5h
0x18008a974  jz      short loc_18008A9B7
0x18008a976  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a97d  cmp     rcx, r13
0x18008a980  jz      loc_18008AA74
0x18008a986  test    byte ptr [rcx+6Ch], 4
0x18008a98a  jz      loc_18008AA40
0x18008a990  cmp     byte ptr [rcx+69h], 1
0x18008a994  jb      loc_18008AA40
0x18008a99a  mov     edx, 6Bh ; 'k'
0x18008a99f  mov     r9d, eax
0x18008a9a2  mov     rcx, [rcx+60h]
0x18008a9a6  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x18008a9ad  call    WPP_SF_d
0x18008a9b2  jmp     loc_18008AA39
0x18008a9b7  mov     rcx, [rdi+18h]; hFile
0x18008a9bb  lea     r8, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18008a9c0  mov     r9d, 1; bWait
0x18008a9c6  mov     rdx, rbp; lpOverlapped
0x18008a9c9  call    cs:__imp_GetOverlappedResult
0x18008a9cf  test    eax, eax
0x18008a9d1  jnz     short loc_18008A9FE
0x18008a9d3  call    cs:__imp_GetLastError
0x18008a9d9  mov     ebx, eax
0x18008a9db  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a9e2  cmp     rcx, r13
0x18008a9e5  jz      loc_18008AA74
0x18008a9eb  test    byte ptr [rcx+6Ch], 4
0x18008a9ef  jz      short loc_18008AA40
0x18008a9f1  cmp     byte ptr [rcx+69h], 1
0x18008a9f5  jb      short loc_18008AA40
0x18008a9f7  mov     edx, 6Ch ; 'l'
0x18008a9fc  jmp     short loc_18008A99F
0x18008a9fe  mov     ecx, [rsp+58h+NumberOfBytesTransferred]
0x18008aa02  cmp     ecx, esi
0x18008aa04  jz      short loc_18008AA30
0x18008aa06  mov     ebx, 306h
0x18008aa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008aa12  cmp     rcx, r13
0x18008aa15  jz      short loc_18008AA74
0x18008aa17  test    byte ptr [rcx+6Ch], 4
0x18008aa1b  jz      short loc_18008AA40
0x18008aa1d  cmp     byte ptr [rcx+69h], 1
0x18008aa21  jb      short loc_18008AA40
0x18008aa23  mov     edx, 6Dh ; 'm'
0x18008aa28  mov     r9d, ebx
0x18008aa2b  jmp     loc_18008A9A2
0x18008aa30  add     [rdi+40h], rcx
0x18008aa34  xor     ebx, ebx
0x18008aa36  mov     [r14], ecx
0x18008aa39  mov     rcx, cs:WPP_GLOBAL_Control
0x18008aa40  cmp     rcx, r13
0x18008aa43  jz      short loc_18008AA74
0x18008aa45  test    byte ptr [rcx+6Ch], 4
0x18008aa49  jz      short loc_18008AA74
0x18008aa4b  cmp     byte ptr [rcx+69h], 4
0x18008aa4f  jb      short loc_18008AA74
0x18008aa51  mov     eax, [r14]
0x18008aa54  lea     r8, WPP_cacbc209fdf435e986c0ff08ed446cf3_Traceguids
0x18008aa5b  mov     rcx, [rcx+60h]
0x18008aa5f  mov     edx, 6Eh ; 'n'
0x18008aa64  mov     [rsp+58h+var_30], ebx
0x18008aa68  mov     r9, r15
0x18008aa6b  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x18008aa6f  call    WPP_SF_qDD
0x18008aa74  mov     rbp, [rsp+58h+arg_10]
0x18008aa79  mov     eax, ebx
0x18008aa7b  mov     rbx, [rsp+58h+arg_8]
0x18008aa80  add     rsp, 30h
0x18008aa84  pop     r15
0x18008aa86  pop     r14
0x18008aa88  pop     r13
0x18008aa8a  pop     rdi
0x18008aa8b  pop     rsi
0x18008aa8c  retn
```
