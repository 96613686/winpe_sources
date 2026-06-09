# CMsmqVssWriter::UpdateRestoreSeqID(void *)

- ea: `0x180094090`
- end: `0x180094226`
- name: `?UpdateRestoreSeqID@CMsmqVssWriter@@AEAAJPEAX@Z`
- size: `406`
- prototype: `int(CMsmqVssWriter *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800929fc`

## callees

- `0x180016ae8`
- `0x18002c61c`
- `0x18003c644`
- `0x180094090`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800940d2`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800940d2`
- `ADVAPI32!RegSetValueExW` at `0x1800941aa`
- `ADVAPI32!RegSetValueExW` at `0x1800941eb`
- `ADVAPI32!RegSetValueExW` at `0x1800941aa`
- `ADVAPI32!RegSetValueExW` at `0x1800941eb`
- `ADVAPI32!RegQueryValueExW` at `0x180094142`
- `ADVAPI32!RegQueryValueExW` at `0x180094142`
- `ADVAPI32!RegOpenKeyExW` at `0x1800940e9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800940e9`

## string_xrefs

- `0x180094167`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsmqVssWriter::UpdateRestoreSeqID(CMsmqVssWriter *this, void *hTransaction)
{
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  signed int v4; // ebx
  bool v5; // sf
  unsigned __int16 v6; // r8
  LSTATUS v7; // eax
  unsigned int v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  HKEY hKey[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v14; // [rsp+80h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF

  hKey[0] = 0;
  v2 = (const WCHAR *)*((_QWORD *)this + 4);
  if ( hTransaction )
    v3 = RegOpenKeyTransactedW(HKEY_LOCAL_MACHINE, v2, 0, 0xF003Fu, hKey, hTransaction, 0);
  else
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0xF003Fu, hKey);
  v4 = v3;
  v5 = v3 < 0;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v4 = (unsigned __int16)v3 | 0x80070000;
      v5 = 1;
    }
    if ( v5 )
    {
      v6 = 3180;
LABEL_14:
      LogMsgHR(v4, (wchar_t *)L"writer/mqwriter", v6);
    }
  }
  else
  {
    Data = 0;
    cbData = 4;
    v7 = RegQueryValueExW(hKey[0], L"SeqID", 0, 0, (LPBYTE)&Data, &cbData);
    v4 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 < 0 )
      {
        v6 = 3200;
        goto LABEL_14;
      }
    }
    else
    {
      ++Data;
      v8 = MqSysTime();
      if ( Data > v8 )
        v8 = Data;
      v14 = v8;
      v9 = RegSetValueExW(hKey[0], L"SeqID", 0, 4u, (const BYTE *)&v14, 4u);
      v4 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
        if ( v4 < 0 )
        {
          v6 = 3220;
          goto LABEL_14;
        }
      }
      else
      {
        v10 = RegSetValueExW(hKey[0], L"SeqIDAtLastRestore", 0, 4u, (const BYTE *)&v14, 4u);
        v4 = v10;
        if ( !v10 )
        {
          v4 = 0;
          goto LABEL_28;
        }
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
        if ( v4 < 0 )
        {
          v6 = 3240;
          goto LABEL_14;
        }
      }
    }
  }
LABEL_28:
  CRegHandle::~CRegHandle((CRegHandle *)hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180094090  push    rbp
0x180094092  push    rbx
0x180094093  push    rsi
0x180094094  mov     rbp, rsp
0x180094097  sub     rsp, 50h
0x18009409b  mov     [rbp+hKey], 0
0x1800940a3  mov     rax, [rcx+20h]
0x1800940a7  lea     rcx, [rbp+hKey]
0x1800940ab  mov     r9d, 0F003Fh; samDesired
0x1800940b1  xor     r8d, r8d; ulOptions
0x1800940b4  test    rdx, rdx
0x1800940b7  jz      short loc_1800940DA
0x1800940b9  mov     [rsp+50h+pExtendedParemeter], r8; pExtendedParemeter
0x1800940be  mov     [rsp+50h+hTransaction], rdx; hTransaction
0x1800940c3  mov     [rsp+50h+phkResult], rcx; phkResult
0x1800940c8  mov     rdx, rax; lpSubKey
0x1800940cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800940d2  call    cs:__imp_RegOpenKeyTransactedW
0x1800940d8  jmp     short loc_1800940EF
0x1800940da  mov     [rsp+50h+phkResult], rcx; phkResult
0x1800940df  mov     rdx, rax; lpSubKey
0x1800940e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800940e9  call    cs:__imp_RegOpenKeyExW
0x1800940ef  mov     ebx, eax
0x1800940f1  test    eax, eax
0x1800940f3  jz      short loc_180094110
0x1800940f5  jle     short loc_180094102
0x1800940f7  movzx   ebx, bx
0x1800940fa  or      ebx, 80070000h
0x180094100  test    ebx, ebx
0x180094102  jns     loc_180094213
0x180094108  mov     r8d, 0C6Ch
0x18009410e  jmp     short loc_180094167
0x180094110  mov     [rbp+Data], 0
0x180094117  mov     esi, 4
0x18009411c  mov     [rbp+cbData], esi
0x18009411f  lea     rax, [rbp+cbData]
0x180094123  mov     [rsp+50h+hTransaction], rax; lpcbData
0x180094128  lea     rax, [rbp+Data]
0x18009412c  mov     [rsp+50h+phkResult], rax; lpData
0x180094131  xor     r9d, r9d; lpType
0x180094134  xor     r8d, r8d; lpReserved
0x180094137  lea     rdx, aSeqid; "SeqID"
0x18009413e  mov     rcx, [rbp+hKey]; hKey
0x180094142  call    cs:__imp_RegQueryValueExW
0x180094148  mov     ebx, eax
0x18009414a  test    eax, eax
0x18009414c  jz      short loc_18009417A
0x18009414e  jle     short loc_180094159
0x180094150  movzx   ebx, ax
0x180094153  or      ebx, 80070000h
0x180094159  test    ebx, ebx
0x18009415b  jns     loc_180094213
0x180094161  mov     r8d, 0C80h; unsigned __int16
0x180094167  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009416e  mov     ecx, ebx; int
0x180094170  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180094175  jmp     loc_180094213
0x18009417a  inc     [rbp+Data]
0x18009417d  call    ?MqSysTime@@YAKXZ; MqSysTime(void)
0x180094182  cmp     [rbp+Data], eax
0x180094185  cmova   eax, [rbp+Data]
0x180094189  mov     [rbp+arg_10], eax
0x18009418c  mov     dword ptr [rsp+50h+hTransaction], esi; cbData
0x180094190  lea     rax, [rbp+arg_10]
0x180094194  mov     [rsp+50h+phkResult], rax; lpData
0x180094199  mov     r9d, esi; dwType
0x18009419c  xor     r8d, r8d; Reserved
0x18009419f  lea     rdx, aSeqid; "SeqID"
0x1800941a6  mov     rcx, [rbp+hKey]; hKey
0x1800941aa  call    cs:__imp_RegSetValueExW
0x1800941b0  mov     ebx, eax
0x1800941b2  test    eax, eax
0x1800941b4  jz      short loc_1800941CD
0x1800941b6  jle     short loc_1800941C1
0x1800941b8  movzx   ebx, ax
0x1800941bb  or      ebx, 80070000h
0x1800941c1  test    ebx, ebx
0x1800941c3  jns     short loc_180094213
0x1800941c5  mov     r8d, 0C94h
0x1800941cb  jmp     short loc_180094167
0x1800941cd  mov     dword ptr [rsp+50h+hTransaction], esi; cbData
0x1800941d1  lea     rax, [rbp+arg_10]
0x1800941d5  mov     [rsp+50h+phkResult], rax; lpData
0x1800941da  mov     r9d, esi; dwType
0x1800941dd  xor     r8d, r8d; Reserved
0x1800941e0  lea     rdx, aSeqidatlastres; "SeqIDAtLastRestore"
0x1800941e7  mov     rcx, [rbp+hKey]; hKey
0x1800941eb  call    cs:__imp_RegSetValueExW
0x1800941f1  mov     ebx, eax
0x1800941f3  test    eax, eax
0x1800941f5  jz      short loc_180094211
0x1800941f7  jle     short loc_180094202
0x1800941f9  movzx   ebx, ax
0x1800941fc  or      ebx, 80070000h
0x180094202  test    ebx, ebx
0x180094204  jns     short loc_180094213
0x180094206  mov     r8d, 0CA8h
0x18009420c  jmp     loc_180094167
0x180094211  xor     ebx, ebx
0x180094213  lea     rcx, [rbp+hKey]; this
0x180094217  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18009421c  mov     eax, ebx
0x18009421e  add     rsp, 50h
0x180094222  pop     rsi
0x180094223  pop     rbx
0x180094224  pop     rbp
0x180094225  retn
```
