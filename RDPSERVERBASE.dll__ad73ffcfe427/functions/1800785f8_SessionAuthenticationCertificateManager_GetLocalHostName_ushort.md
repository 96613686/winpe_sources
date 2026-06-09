# SessionAuthenticationCertificateManager::GetLocalHostName(ushort * *)

- ea: `0x1800785f8`
- end: `0x1800787fa`
- name: `?GetLocalHostName@SessionAuthenticationCertificateManager@@CAJPEAPEAG@Z`
- size: `514`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801323f0`

## callees

- `0x180077aa0`
- `0x1800785f8`
- `0x180079724`
- `0x180079770`
- `0x18007f6a4`
- `0x18007f6b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007861d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180078721`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007861d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180078721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007862b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007865e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007875b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007862b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007865e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007875b`
- `OLEAUT32!__imp_SysAllocString` at `0x180078780`
- `OLEAUT32!__imp_SysAllocString` at `0x180078780`

## pseudocode

```c
__int64 __fastcall SessionAuthenticationCertificateManager::GetLocalHostName(unsigned __int16 **a1)
{
  OLECHAR *v2; // rsi
  signed int LastError; // eax
  unsigned int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  signed int v7; // eax
  unsigned int v8; // ebx
  WCHAR *v9; // rax
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  signed int v13; // eax
  unsigned __int16 *v14; // rax
  DWORD nSize; // [rsp+48h] [rbp+10h] BYREF

  nSize = 0;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) && GetLastError() != 234 )
  {
    v2 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 10;
LABEL_9:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids,
        CurrentThreadActivityIdPrefix,
        v4);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  v9 = (WCHAR *)operator new(saturated_mul(nSize, 2u));
  v2 = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_30;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 11;
    v12 = "WCHAR";
    goto LABEL_29;
  }
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v9, &nSize) )
  {
    v8 = 0;
    v14 = SysAllocString(v2);
    *a1 = v14;
    if ( v14 )
      goto LABEL_31;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_30:
      v8 = -2147024882;
      goto LABEL_31;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 13;
    v12 = "BSTR";
LABEL_29:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids,
      v10,
      (__int64)v12);
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      v4 = (unsigned __int16)v13 | 0x80070000;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 12;
    goto LABEL_9;
  }
LABEL_10:
  v7 = GetLastError();
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
LABEL_31:
  operator delete(v2);
  return v8;
}

```

## disassembly

```asm
0x1800785f8  mov     rax, rsp
0x1800785fb  mov     [rax+8], rbx
0x1800785ff  mov     [rax+18h], rsi
0x180078603  push    rdi
0x180078604  sub     rsp, 30h
0x180078608  xor     edx, edx; lpBuffer
0x18007860a  mov     dword ptr [rax+10h], 0
0x180078611  mov     rdi, rcx
0x180078614  lea     r8, [rax+10h]; nSize
0x180078618  lea     ebx, [rdx+3]
0x18007861b  mov     ecx, ebx; NameType
0x18007861d  call    cs:__imp_GetComputerNameExW
0x180078623  test    eax, eax
0x180078625  jnz     loc_1800786B1
0x18007862b  call    cs:__imp_GetLastError
0x180078631  cmp     eax, 0EAh
0x180078636  jz      short loc_1800786B1
0x180078638  xor     esi, esi
0x18007863a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078641  lea     rax, WPP_GLOBAL_Control
0x180078648  mov     edi, 80070000h
0x18007864d  cmp     rcx, rax
0x180078650  jz      short loc_180078697
0x180078652  test    byte ptr [rcx+1Ch], 8
0x180078656  jz      short loc_180078697
0x180078658  cmp     byte ptr [rcx+19h], 2
0x18007865c  jb      short loc_180078697
0x18007865e  call    cs:__imp_GetLastError
0x180078664  mov     ebx, eax
0x180078666  test    eax, eax
0x180078668  jle     short loc_18007866F
0x18007866a  movzx   ebx, ax
0x18007866d  or      ebx, edi
0x18007866f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078674  mov     edx, 0Ah
0x180078679  mov     rcx, cs:WPP_GLOBAL_Control
0x180078680  lea     r8, WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids
0x180078687  mov     r9d, eax
0x18007868a  mov     dword ptr [rsp+38h+var_18], ebx
0x18007868e  mov     rcx, [rcx+10h]
0x180078692  call    WPP_SF_Dd
0x180078697  call    cs:__imp_GetLastError
0x18007869d  mov     ebx, eax
0x18007869f  test    eax, eax
0x1800786a1  jle     loc_1800787E0
0x1800786a7  movzx   ebx, ax
0x1800786aa  or      ebx, edi
0x1800786ac  jmp     loc_1800787E0
0x1800786b1  mov     ecx, [rsp+38h+nSize]
0x1800786b5  mov     eax, 2
0x1800786ba  mul     rcx
0x1800786bd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800786c4  cmovb   rax, rcx
0x1800786c8  mov     rcx, rax; Size
0x1800786cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800786d0  mov     rsi, rax
0x1800786d3  test    rax, rax
0x1800786d6  jnz     short loc_180078717
0x1800786d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800786df  lea     rax, WPP_GLOBAL_Control
0x1800786e6  cmp     rcx, rax
0x1800786e9  jz      loc_1800787DB
0x1800786ef  test    byte ptr [rcx+1Ch], 8
0x1800786f3  jz      loc_1800787DB
0x1800786f9  cmp     byte ptr [rcx+19h], 2
0x1800786fd  jb      loc_1800787DB
0x180078703  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078708  lea     edx, [rsi+0Bh]
0x18007870b  lea     rcx, aWchar; "WCHAR"
0x180078712  jmp     loc_1800787BC
0x180078717  lea     r8, [rsp+38h+nSize]; nSize
0x18007871c  mov     rdx, rsi; lpBuffer
0x18007871f  mov     ecx, ebx; NameType
0x180078721  call    cs:__imp_GetComputerNameExW
0x180078727  test    eax, eax
0x180078729  jnz     short loc_18007877B
0x18007872b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078732  lea     rax, WPP_GLOBAL_Control
0x180078739  mov     edi, 80070000h
0x18007873e  cmp     rcx, rax
0x180078741  jz      loc_180078697
0x180078747  test    byte ptr [rcx+1Ch], 8
0x18007874b  jz      loc_180078697
0x180078751  cmp     byte ptr [rcx+19h], 2
0x180078755  jb      loc_180078697
0x18007875b  call    cs:__imp_GetLastError
0x180078761  mov     ebx, eax
0x180078763  test    eax, eax
0x180078765  jle     short loc_18007876C
0x180078767  movzx   ebx, ax
0x18007876a  or      ebx, edi
0x18007876c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180078771  mov     edx, 0Ch
0x180078776  jmp     loc_180078679
0x18007877b  mov     rcx, rsi; psz
0x18007877e  xor     ebx, ebx
0x180078780  call    cs:__imp_SysAllocString
0x180078786  mov     [rdi], rax
0x180078789  test    rax, rax
0x18007878c  jnz     short loc_1800787E0
0x18007878e  mov     rcx, cs:WPP_GLOBAL_Control
0x180078795  lea     rax, WPP_GLOBAL_Control
0x18007879c  cmp     rcx, rax
0x18007879f  jz      short loc_1800787DB
0x1800787a1  test    byte ptr [rcx+1Ch], 8
0x1800787a5  jz      short loc_1800787DB
0x1800787a7  cmp     byte ptr [rcx+19h], 2
0x1800787ab  jb      short loc_1800787DB
0x1800787ad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800787b2  lea     edx, [rbx+0Dh]
0x1800787b5  lea     rcx, aBstr; "BSTR"
0x1800787bc  mov     [rsp+38h+var_18], rcx
0x1800787c1  lea     r8, WPP_9aadc3863c713c7f2b2f111ffc40317d_Traceguids
0x1800787c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787cf  mov     r9d, eax
0x1800787d2  mov     rcx, [rcx+10h]
0x1800787d6  call    WPP_SF_Ds
0x1800787db  mov     ebx, 8007000Eh
0x1800787e0  mov     rcx, rsi; Block
0x1800787e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800787e8  mov     rsi, [rsp+38h+arg_10]
0x1800787ed  mov     eax, ebx
0x1800787ef  mov     rbx, [rsp+38h+arg_0]
0x1800787f4  add     rsp, 30h
0x1800787f8  pop     rdi
0x1800787f9  retn
```
