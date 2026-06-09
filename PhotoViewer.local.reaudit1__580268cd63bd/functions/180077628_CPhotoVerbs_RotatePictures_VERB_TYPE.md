# CPhotoVerbs::_RotatePictures(VERB_TYPE)

- ea: `0x180077628`
- end: `0x1800776f9`
- name: `?_RotatePictures@CPhotoVerbs@@AEAAXW4VERB_TYPE@@@Z`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180077270`

## callees

- `0x18007756c`
- `0x180077628`

## import_xrefs

- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180077689`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180077689`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800776bc`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800776db`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800776bc`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800776db`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180077643`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180077643`

## pseudocode

```c
int __fastcall CPhotoVerbs::_RotatePictures(__int64 a1, unsigned __int64 a2, bool a3)
{
  int v3; // edi
  LPSTREAM *v5; // rax
  LPSTREAM *v6; // rbx
  IUnknown *v7; // rdx
  HRESULT v8; // eax

  v3 = a2;
  LOBYTE(a2) = 1;
  v5 = (LPSTREAM *)BasePrivate::New((BasePrivate *)0x28, a2, a3);
  v6 = v5;
  if ( v5 )
  {
    v7 = *(IUnknown **)(a1 + 104);
    *v5 = (LPSTREAM)&CRunVerbOnThread::`vftable';
    v5[1] = 0;
    *((_DWORD *)v5 + 4) = 1;
    v5[3] = 0;
    v8 = CoMarshalInterThreadInterfaceInStream(&GUID_0000010e_0000_0000_c000_000000000046, v7, v5 + 3);
    *((_DWORD *)v6 + 8) = v3;
    *v6 = (LPSTREAM)&CRotateThreadProc::`vftable';
    if ( v8 >= 0 && !SHCreateThread(CRunVerbOnThread::s_ThreadProc, v6, 0x1Eu, CRunVerbOnThread::s_ThreadSyncProc) )
      SHCreateThread(CRunVerbOnThread::s_ThreadProc, v6, 0x1Cu, CRunVerbOnThread::s_ThreadSyncProc);
    LODWORD(v5) = CRunVerbOnThread::Release((CRunVerbOnThread *)v6);
  }
  return (int)v5;
}

```

## disassembly

```asm
0x180077628  mov     [rsp+arg_0], rbx
0x18007762d  mov     [rsp+arg_8], rsi
0x180077632  push    rdi
0x180077633  sub     rsp, 20h
0x180077637  mov     edi, edx
0x180077639  mov     rsi, rcx
0x18007763c  mov     dl, 1
0x18007763e  mov     ecx, 28h ; '('
0x180077643  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180077649  mov     [rsp+28h+arg_10], rax
0x18007764e  mov     rbx, rax
0x180077651  test    rax, rax
0x180077654  jz      loc_1800776E9
0x18007765a  mov     rdx, [rsi+68h]; pUnk
0x18007765e  lea     rax, ??_7CRunVerbOnThread@@6B@; const CRunVerbOnThread::`vftable'
0x180077665  mov     [rbx], rax
0x180077668  lea     r8, [rbx+18h]; ppStm
0x18007766c  mov     qword ptr [rbx+8], 0
0x180077674  lea     rcx, _GUID_0000010e_0000_0000_c000_000000000046; riid
0x18007767b  mov     dword ptr [rbx+10h], 1
0x180077682  mov     qword ptr [r8], 0
0x180077689  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18007768f  mov     [rbx+20h], edi
0x180077692  lea     rcx, ??_7CRotateThreadProc@@6B@; const CRotateThreadProc::`vftable'
0x180077699  mov     [rbx], rcx
0x18007769c  test    rbx, rbx
0x18007769f  jz      short loc_1800776E9
0x1800776a1  test    eax, eax
0x1800776a3  js      short loc_1800776E1
0x1800776a5  lea     r9, ?s_ThreadSyncProc@CRunVerbOnThread@@CAKPEAX@Z; pfnCallback
0x1800776ac  mov     r8d, 1Eh; flags
0x1800776b2  mov     rdx, rbx; pData
0x1800776b5  lea     rcx, ?s_ThreadProc@CRunVerbOnThread@@CAKPEAX@Z; pfnThreadProc
0x1800776bc  call    cs:__imp_SHCreateThread
0x1800776c2  test    eax, eax
0x1800776c4  jnz     short loc_1800776E1
0x1800776c6  lea     r9, ?s_ThreadSyncProc@CRunVerbOnThread@@CAKPEAX@Z; pfnCallback
0x1800776cd  mov     rdx, rbx; pData
0x1800776d0  lea     r8d, [rax+1Ch]; flags
0x1800776d4  lea     rcx, ?s_ThreadProc@CRunVerbOnThread@@CAKPEAX@Z; pfnThreadProc
0x1800776db  call    cs:__imp_SHCreateThread
0x1800776e1  mov     rcx, rbx; this
0x1800776e4  call    ?Release@CRunVerbOnThread@@QEAAKXZ; CRunVerbOnThread::Release(void)
0x1800776e9  mov     rbx, [rsp+28h+arg_0]
0x1800776ee  mov     rsi, [rsp+28h+arg_8]
0x1800776f3  add     rsp, 20h
0x1800776f7  pop     rdi
0x1800776f8  retn
```
