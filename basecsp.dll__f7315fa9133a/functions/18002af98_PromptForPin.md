# PromptForPin

- ea: `0x18002af98`
- end: `0x18002b124`
- name: `PromptForPin`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b1a4`

## callees

- `0x18000a772`
- `0x18000de80`
- `0x18002ab38`
- `0x18002abe8`
- `0x18002ad94`
- `0x18002af98`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002b10e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002b10e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b0f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b0f2`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x18002b093`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x18002b093`

## pseudocode

```c
__int64 __fastcall PromptForPin(__int64 a1)
{
  void *v2; // r14
  struct _TP_TIMER *v3; // rsi
  const WCHAR *v4; // rax
  DWORD v5; // edi
  unsigned int v6; // ecx
  _BYTE *v7; // rcx
  __int64 v8; // rax
  LPVOID pv; // [rsp+50h] [rbp-79h] BYREF
  void *v11; // [rsp+58h] [rbp-71h] BYREF
  struct _TP_TIMER *v12; // [rsp+60h] [rbp-69h] BYREF
  struct _CREDUI_INFOW pUiInfo; // [rsp+70h] [rbp-59h] BYREF
  _QWORD v14[11]; // [rsp+C8h] [rbp-1h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+130h] [rbp+67h] BYREF
  ULONG ulInAuthBufferSize; // [rsp+138h] [rbp+6Fh] BYREF
  ULONG pulAuthPackage; // [rsp+140h] [rbp+77h] BYREF
  LPCVOID pvInAuthBuffer; // [rsp+148h] [rbp+7Fh] BYREF

  pvInAuthBuffer = 0;
  ulInAuthBufferSize = 0;
  v2 = 0;
  pv = 0;
  v3 = 0;
  pulOutAuthBufferSize = 0;
  pulAuthPackage = -5324;
  v11 = 0;
  v12 = 0;
  memset_0(&pUiInfo, 0, 0x88u);
  pUiInfo.hwndParent = *(HWND *)(a1 + 16);
  pUiInfo.pszMessageText = *(PCWSTR *)(a1 + 56);
  v4 = *(const WCHAR **)(a1 + 48);
  pUiInfo.cbSize = 136;
  if ( v4 )
    pUiInfo.pszCaptionText = v4;
  else
    pUiInfo.pszCaptionText = **(PCWSTR **)a1;
  v5 = I_FormatAndAllocateKerbCertificateLogon(a1, &pvInAuthBuffer, &ulInAuthBufferSize);
  if ( !v5 )
  {
    v6 = *(_DWORD *)(a1 + 124);
    if ( v6 )
    {
      GetAbortEvent(v6, &v11, &v12, v14);
      v2 = v11;
      v3 = v12;
    }
    v5 = CredUIPromptForWindowsCredentialsW(
           &pUiInfo,
           0,
           &pulAuthPackage,
           pvInAuthBuffer,
           ulInAuthBufferSize,
           &pv,
           &pulOutAuthBufferSize,
           0,
           *(_DWORD *)(a1 + 120) | 0x20);
    if ( !v5 )
    {
      if ( pulAuthPackage == -5324 )
        v5 = I_UnpackPin(a1, pv, pulOutAuthBufferSize);
      else
        v5 = 1359;
    }
  }
  if ( pvInAuthBuffer )
    CspFreeH(pvInAuthBuffer);
  v7 = pv;
  if ( pv )
  {
    v8 = pulOutAuthBufferSize;
    if ( pulOutAuthBufferSize )
    {
      do
      {
        *v7++ = 0;
        --v8;
      }
      while ( v8 );
      v7 = pv;
    }
    CoTaskMemFree(v7);
  }
  if ( v2 )
    CloseHandle(v2);
  if ( v3 )
    CloseThreadpoolTimer(v3);
  return v5;
}

```

## disassembly

```asm
0x18002af98  push    rbp
0x18002af9a  push    rbx
0x18002af9b  push    rsi
0x18002af9c  push    rdi
0x18002af9d  push    r14
0x18002af9f  lea     rbp, [rsp-37h]
0x18002afa4  sub     rsp, 100h
0x18002afab  mov     rbx, rcx
0x18002afae  mov     [rbp+57h+pvInAuthBuffer], 0
0x18002afb6  mov     edi, 88h
0x18002afbb  mov     [rbp+57h+arg_8], 0
0x18002afc2  xor     r14d, r14d
0x18002afc5  mov     [rbp+57h+pv], 0
0x18002afcd  xor     esi, esi
0x18002afcf  mov     [rbp+57h+arg_0], 0
0x18002afd6  mov     r8d, edi; Size
0x18002afd9  mov     [rbp+57h+pulAuthPackage], 0FFFFEB34h
0x18002afe0  xor     edx, edx; Val
0x18002afe2  mov     [rbp+57h+var_C8], r14
0x18002afe6  lea     rcx, [rbp+57h+pUiInfo]; void *
0x18002afea  mov     [rbp+57h+var_C0], rsi
0x18002afee  call    memset_0
0x18002aff3  mov     rax, [rbx+10h]
0x18002aff7  mov     [rbp+57h+pUiInfo.hwndParent], rax
0x18002affb  mov     rax, [rbx+38h]
0x18002afff  mov     [rbp+57h+pUiInfo.pszMessageText], rax
0x18002b003  mov     rax, [rbx+30h]
0x18002b007  mov     [rbp+57h+pUiInfo.cbSize], edi
0x18002b00a  test    rax, rax
0x18002b00d  jz      short loc_18002B015
0x18002b00f  mov     [rbp+57h+pUiInfo.pszCaptionText], rax
0x18002b013  jmp     short loc_18002B01F
0x18002b015  mov     rax, [rbx]
0x18002b018  mov     rcx, [rax]
0x18002b01b  mov     [rbp+57h+pUiInfo.pszCaptionText], rcx
0x18002b01f  lea     r8, [rbp+57h+arg_8]
0x18002b023  mov     rcx, rbx
0x18002b026  lea     rdx, [rbp+57h+pvInAuthBuffer]
0x18002b02a  call    I_FormatAndAllocateKerbCertificateLogon
0x18002b02f  mov     edi, eax
0x18002b031  test    eax, eax
0x18002b033  jnz     loc_18002B0C1
0x18002b039  mov     ecx, [rbx+7Ch]
0x18002b03c  test    ecx, ecx
0x18002b03e  jz      short loc_18002B059
0x18002b040  lea     r9, [rbp+57h+var_58]
0x18002b044  lea     r8, [rbp+57h+var_C0]
0x18002b048  lea     rdx, [rbp+57h+var_C8]
0x18002b04c  call    GetAbortEvent
0x18002b051  mov     r14, [rbp+57h+var_C8]
0x18002b055  mov     rsi, [rbp+57h+var_C0]
0x18002b059  mov     eax, [rbx+78h]
0x18002b05c  lea     r8, [rbp+57h+pulAuthPackage]; pulAuthPackage
0x18002b060  mov     r9, [rbp+57h+pvInAuthBuffer]; pvInAuthBuffer
0x18002b064  lea     rcx, [rbp+57h+pUiInfo]; pUiInfo
0x18002b068  or      eax, 20h
0x18002b06b  xor     edx, edx; dwAuthError
0x18002b06d  mov     [rsp+120h+dwFlags], eax; dwFlags
0x18002b071  lea     rax, [rbp+57h+arg_0]
0x18002b075  mov     [rsp+120h+pfSave], 0; pfSave
0x18002b07e  mov     [rsp+120h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x18002b083  lea     rax, [rbp+57h+pv]
0x18002b087  mov     [rsp+120h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x18002b08c  mov     eax, [rbp+57h+arg_8]
0x18002b08f  mov     [rsp+120h+ulInAuthBufferSize], eax; ulInAuthBufferSize
0x18002b093  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x18002b099  mov     edi, eax
0x18002b09b  test    eax, eax
0x18002b09d  jnz     short loc_18002B0C1
0x18002b09f  cmp     [rbp+57h+pulAuthPackage], 0FFFFEB34h
0x18002b0a6  jz      short loc_18002B0AF
0x18002b0a8  mov     edi, 54Fh
0x18002b0ad  jmp     short loc_18002B0C1
0x18002b0af  mov     r8d, [rbp+57h+arg_0]
0x18002b0b3  mov     rcx, rbx
0x18002b0b6  mov     rdx, [rbp+57h+pv]
0x18002b0ba  call    I_UnpackPin
0x18002b0bf  mov     edi, eax
0x18002b0c1  cmp     [rbp+57h+pvInAuthBuffer], 0
0x18002b0c6  jz      short loc_18002B0D1
0x18002b0c8  mov     rcx, [rbp+57h+pvInAuthBuffer]
0x18002b0cc  call    CspFreeH
0x18002b0d1  mov     rcx, [rbp+57h+pv]
0x18002b0d5  test    rcx, rcx
0x18002b0d8  jz      short loc_18002B0F8
0x18002b0da  mov     eax, [rbp+57h+arg_0]
0x18002b0dd  test    rax, rax
0x18002b0e0  jz      short loc_18002B0F2
0x18002b0e2  mov     byte ptr [rcx], 0
0x18002b0e5  inc     rcx
0x18002b0e8  sub     rax, 1
0x18002b0ec  jnz     short loc_18002B0E2
0x18002b0ee  mov     rcx, [rbp+57h+pv]; pv
0x18002b0f2  call    cs:__imp_CoTaskMemFree
0x18002b0f8  test    r14, r14
0x18002b0fb  jz      short loc_18002B106
0x18002b0fd  mov     rcx, r14; hObject
0x18002b100  call    cs:__imp_CloseHandle
0x18002b106  test    rsi, rsi
0x18002b109  jz      short loc_18002B114
0x18002b10b  mov     rcx, rsi; pti
0x18002b10e  call    cs:__imp_CloseThreadpoolTimer
0x18002b114  mov     eax, edi
0x18002b116  add     rsp, 100h
0x18002b11d  pop     r14
0x18002b11f  pop     rdi
0x18002b120  pop     rsi
0x18002b121  pop     rbx
0x18002b122  pop     rbp
0x18002b123  retn
```
