# DavFsQueryVolumeInformation

- ea: `0x180023960`
- end: `0x180023c47`
- name: `DavFsQueryVolumeInformation`
- size: `743`
- prototype: `__int64 __fastcall(_QWORD *pvCallbackContext)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`
- `0x18000b93c`
- `0x18000bc5c`
- `0x18000bfe0`
- `0x18000d9e4`
- `0x180010478`
- `0x180010770`
- `0x180011360`
- `0x180023960`
- `0x1800297e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023b62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023bba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023b62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023bba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023ae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023ae5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023bc0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023bc0`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x180023a5f`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x180023a5f`
- `WINHTTP!WinHttpCloseHandle` at `0x180023be4`
- `WINHTTP!WinHttpCloseHandle` at `0x180023be4`

## pseudocode

```c
__int64 __fastcall DavFsQueryVolumeInformation(_QWORD *pvCallbackContext)
{
  __int64 v1; // r14
  WCHAR *v3; // r14
  unsigned int v4; // esi
  _QWORD *v5; // rcx
  unsigned int v6; // r15d
  __int64 v7; // rsi
  unsigned int v8; // eax
  __int64 *v9; // rsi
  int v10; // eax
  void *v11; // rcx
  DWORD LastError; // eax
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 *v15; // [rsp+68h] [rbp+10h] BYREF

  v1 = pvCallbackContext[79];
  v15 = 0;
  v14 = 0;
  v3 = (WCHAR *)(v1 + 2);
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids);
    v4 = 87;
    goto LABEL_35;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v3);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *((_DWORD *)pvCallbackContext + 164);
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
  {
    WPP_SF_d(v5[2], 53, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v6);
    v5 = WPP_GLOBAL_Control;
  }
  v7 = pvCallbackContext[80];
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
    WPP_SF_S(v5[2], 55, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v7 + 2);
  DavRemoveDummyShareFromFileName(v7 + 2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids,
      *((unsigned int *)pvCallbackContext + 162),
      *((_DWORD *)pvCallbackContext + 163));
  v8 = UMReflectorImpersonate(pvCallbackContext, pvCallbackContext[9]);
  v4 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v8);
      goto LABEL_35;
    }
  }
  else
  {
    EnterCriticalSection(&HashServerEntryTableLock);
    if ( (unsigned int)DavDoesUserEntryExist(v3, v6, (_DWORD *)pvCallbackContext + 162, &v15, (__int64 **)&v14)
      && v14
      && (v9 = v15) != 0 )
    {
      pvCallbackContext[63] = v14;
      pvCallbackContext[62] = v9;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v9);
      ++*((_DWORD *)v9 + 16);
      LeaveCriticalSection(&HashServerEntryTableLock);
      *((_DWORD *)pvCallbackContext + 13) = 0;
      *((_DWORD *)pvCallbackContext + 14) = 1;
      pvCallbackContext[62] = v9;
      v4 = DavAsyncCommonStates((unsigned int *)pvCallbackContext);
    }
    else
    {
      v4 = 1223;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids);
      LeaveCriticalSection(&HashServerEntryTableLock);
    }
    RevertToSelf();
  }
  if ( !v4 )
  {
    v10 = 0;
    goto LABEL_37;
  }
LABEL_35:
  v10 = DavMapErrorToNtStatus(v4);
LABEL_37:
  *((_DWORD *)pvCallbackContext + 8) = v10;
  v11 = (void *)pvCallbackContext[64];
  if ( v11 )
  {
    if ( !WinHttpCloseHandle(v11) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, LastError);
    }
  }
  DavFsFinalizeTheDavCallBackContext(pvCallbackContext);
  if ( pvCallbackContext[62] )
    DavFinalizePerUserEntry(pvCallbackContext + 62);
  return v4;
}

```

## disassembly

```asm
0x180023960  mov     [rsp+arg_10], rbx
0x180023965  push    rbp
0x180023966  push    rsi
0x180023967  push    rdi
0x180023968  push    r14
0x18002396a  push    r15
0x18002396c  sub     rsp, 30h
0x180023970  mov     r14, [rcx+278h]
0x180023977  mov     rbx, rcx
0x18002397a  mov     [rsp+58h+arg_8], 0
0x180023983  mov     [rsp+58h+arg_0], 0
0x18002398c  add     r14, 2
0x180023990  jnz     short loc_1800239CC
0x180023992  mov     rcx, cs:WPP_GLOBAL_Control
0x180023999  lea     rdi, WPP_GLOBAL_Control
0x1800239a0  lea     rbp, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x1800239a7  cmp     rcx, rdi
0x1800239aa  jz      short loc_1800239C2
0x1800239ac  test    byte ptr [rcx+1Ch], 1
0x1800239b0  jz      short loc_1800239C2
0x1800239b2  mov     rcx, [rcx+10h]
0x1800239b6  lea     edx, [r14+33h]
0x1800239ba  mov     r8, rbp
0x1800239bd  call    WPP_SF_
0x1800239c2  mov     esi, 57h ; 'W'
0x1800239c7  jmp     loc_180023BCA
0x1800239cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239d3  lea     rdi, WPP_GLOBAL_Control
0x1800239da  lea     rbp, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x1800239e1  cmp     rcx, rdi
0x1800239e4  jz      short loc_180023A07
0x1800239e6  test    byte ptr [rcx+1Ch], 2
0x1800239ea  jz      short loc_180023A07
0x1800239ec  mov     rcx, [rcx+10h]
0x1800239f0  mov     edx, 34h ; '4'
0x1800239f5  mov     r9, r14
0x1800239f8  mov     r8, rbp
0x1800239fb  call    WPP_SF_S
0x180023a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a07  mov     r15d, [rbx+290h]
0x180023a0e  cmp     rcx, rdi
0x180023a11  jz      short loc_180023A34
0x180023a13  test    byte ptr [rcx+1Ch], 2
0x180023a17  jz      short loc_180023A34
0x180023a19  mov     rcx, [rcx+10h]
0x180023a1d  mov     edx, 35h ; '5'
0x180023a22  mov     r9d, r15d
0x180023a25  mov     r8, rbp
0x180023a28  call    WPP_SF_d
0x180023a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a34  mov     rsi, [rbx+280h]
0x180023a3b  cmp     rcx, rdi
0x180023a3e  jz      short loc_180023A5B
0x180023a40  test    byte ptr [rcx+1Ch], 2
0x180023a44  jz      short loc_180023A5B
0x180023a46  mov     rcx, [rcx+10h]
0x180023a4a  lea     r9, [rsi+2]
0x180023a4e  mov     edx, 37h ; '7'
0x180023a53  mov     r8, rbp
0x180023a56  call    WPP_SF_S
0x180023a5b  lea     rcx, [rsi+2]
0x180023a5f  call    cs:__imp_DavRemoveDummyShareFromFileName
0x180023a65  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a6c  cmp     rcx, rdi
0x180023a6f  jz      short loc_180023A99
0x180023a71  test    byte ptr [rcx+1Ch], 2
0x180023a75  jz      short loc_180023A99
0x180023a77  mov     eax, [rbx+28Ch]
0x180023a7d  mov     edx, 38h ; '8'
0x180023a82  mov     r9d, [rbx+288h]
0x180023a89  mov     r8, rbp
0x180023a8c  mov     rcx, [rcx+10h]
0x180023a90  mov     dword ptr [rsp+58h+var_38], eax
0x180023a94  call    WPP_SF_Dd
0x180023a99  mov     rdx, [rbx+48h]
0x180023a9d  mov     rcx, rbx
0x180023aa0  call    UMReflectorImpersonate
0x180023aa5  mov     esi, eax
0x180023aa7  test    eax, eax
0x180023aa9  jz      short loc_180023ADE
0x180023aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ab2  cmp     rcx, rdi
0x180023ab5  jz      loc_180023BC6
0x180023abb  test    byte ptr [rcx+1Ch], 1
0x180023abf  jz      loc_180023BC6
0x180023ac5  mov     rcx, [rcx+10h]
0x180023ac9  mov     edx, 39h ; '9'
0x180023ace  mov     r9d, eax
0x180023ad1  mov     r8, rbp
0x180023ad4  call    WPP_SF_d
0x180023ad9  jmp     loc_180023BCA
0x180023ade  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x180023ae5  call    cs:__imp_EnterCriticalSection
0x180023aeb  lea     rax, [rsp+58h+arg_0]
0x180023af0  mov     edx, r15d
0x180023af3  lea     r8, [rbx+288h]
0x180023afa  mov     [rsp+58h+var_38], rax; __int64
0x180023aff  lea     r9, [rsp+58h+arg_8]
0x180023b04  mov     rcx, r14; hMem
0x180023b07  call    DavDoesUserEntryExist
0x180023b0c  test    eax, eax
0x180023b0e  jz      short loc_180023B8B
0x180023b10  mov     rax, [rsp+58h+arg_0]
0x180023b15  test    rax, rax
0x180023b18  jz      short loc_180023B8B
0x180023b1a  mov     rsi, [rsp+58h+arg_8]
0x180023b1f  test    rsi, rsi
0x180023b22  jz      short loc_180023B8B
0x180023b24  mov     [rbx+1F8h], rax
0x180023b2b  mov     [rbx+1F0h], rsi
0x180023b32  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b39  cmp     rcx, rdi
0x180023b3c  jz      short loc_180023B58
0x180023b3e  test    byte ptr [rcx+1Ch], 2
0x180023b42  jz      short loc_180023B58
0x180023b44  mov     rcx, [rcx+10h]
0x180023b48  mov     edx, 3Bh ; ';'
0x180023b4d  mov     r9, rsi
0x180023b50  mov     r8, rbp
0x180023b53  call    WPP_SF_q
0x180023b58  inc     dword ptr [rsi+40h]
0x180023b5b  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x180023b62  call    cs:__imp_LeaveCriticalSection
0x180023b68  xor     edx, edx
0x180023b6a  mov     dword ptr [rbx+34h], 0
0x180023b71  mov     rcx, rbx; pvCallbackContext
0x180023b74  mov     dword ptr [rbx+38h], 1
0x180023b7b  mov     [rbx+1F0h], rsi
0x180023b82  call    DavAsyncCommonStates
0x180023b87  mov     esi, eax
0x180023b89  jmp     short loc_180023BC0
0x180023b8b  mov     esi, 4C7h
0x180023b90  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b97  cmp     rcx, rdi
0x180023b9a  jz      short loc_180023BB3
0x180023b9c  test    byte ptr [rcx+1Ch], 1
0x180023ba0  jz      short loc_180023BB3
0x180023ba2  mov     rcx, [rcx+10h]
0x180023ba6  mov     edx, 3Ah ; ':'
0x180023bab  mov     r8, rbp
0x180023bae  call    WPP_SF_
0x180023bb3  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x180023bba  call    cs:__imp_LeaveCriticalSection
0x180023bc0  call    cs:__imp_RevertToSelf
0x180023bc6  test    esi, esi
0x180023bc8  jz      short loc_180023BD3
0x180023bca  mov     ecx, esi
0x180023bcc  call    DavMapErrorToNtStatus
0x180023bd1  jmp     short loc_180023BD5
0x180023bd3  xor     eax, eax
0x180023bd5  mov     [rbx+20h], eax
0x180023bd8  mov     rcx, [rbx+200h]; hInternet
0x180023bdf  test    rcx, rcx
0x180023be2  jz      short loc_180023C1A
0x180023be4  call    cs:__imp_WinHttpCloseHandle
0x180023bea  test    eax, eax
0x180023bec  jnz     short loc_180023C1A
0x180023bee  call    cs:__imp_GetLastError
0x180023bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bfb  cmp     rcx, rdi
0x180023bfe  jz      short loc_180023C1A
0x180023c00  test    byte ptr [rcx+1Ch], 1
0x180023c04  jz      short loc_180023C1A
0x180023c06  mov     rcx, [rcx+10h]
0x180023c0a  mov     edx, 3Ch ; '<'
0x180023c0f  mov     r9d, eax
0x180023c12  mov     r8, rbp
0x180023c15  call    WPP_SF_d
0x180023c1a  mov     rcx, rbx
0x180023c1d  call    DavFsFinalizeTheDavCallBackContext
0x180023c22  lea     rcx, [rbx+1F0h]
0x180023c29  cmp     qword ptr [rcx], 0
0x180023c2d  jz      short loc_180023C34
0x180023c2f  call    DavFinalizePerUserEntry
0x180023c34  mov     rbx, [rsp+58h+arg_10]
0x180023c39  mov     eax, esi
0x180023c3b  add     rsp, 30h
0x180023c3f  pop     r15
0x180023c41  pop     r14
0x180023c43  pop     rdi
0x180023c44  pop     rsi
0x180023c45  pop     rbp
0x180023c46  retn
```
