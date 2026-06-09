# SetErrorInfoDaemon

- ea: `0x140028460`
- end: `0x140028565`
- name: `SetErrorInfoDaemon`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x140005240`
- `0x14000e898`
- `0x140016098`
- `0x140028460`
- `0x14004e6e0`
- `0x140070010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x140028519`
- `OLEAUT32!__imp_SetErrorInfo` at `0x140028519`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1400284a4`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1400284a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetErrorInfoDaemon(DWORD dwMessageId)
{
  int v2; // r8d
  ICreateErrorInfo *v3; // rdi
  HRESULT (__stdcall *SetDescription)(ICreateErrorInfo *, LPOLESTR); // rbx
  wchar_t *Buffer; // rax
  ICreateErrorInfo *pperrinfo; // [rsp+28h] [rbp-E0h] BYREF
  IErrorInfo *perrinfo[3]; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v9[260]; // [rsp+48h] [rbp-C0h] BYREF

  perrinfo[1] = (IErrorInfo *)-2LL;
  pperrinfo = 0;
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    CErrorString::CErrorString((CErrorString *)v9, dwMessageId, v2);
    v3 = pperrinfo;
    SetDescription = pperrinfo->lpVtbl->SetDescription;
    Buffer = CLMString::GetBuffer((CLMString *)v9, 0);
    if ( ((int (__fastcall *)(ICreateErrorInfo *, wchar_t *))SetDescription)(v3, Buffer) >= 0 )
    {
      perrinfo[0] = 0;
      if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
             pperrinfo,
             &IID_IErrorInfo,
             perrinfo) >= 0 )
        SetErrorInfo(0, perrinfo[0]);
      TComPointer<IBindCtx>::~TComPointer<IBindCtx>(perrinfo);
    }
    v9[0] = &CLMString::`vftable';
  }
  return TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&pperrinfo);
}

```

## disassembly

```asm
0x140028460  mov     rax, rsp
0x140028463  push    rbp
0x140028464  lea     rbp, [rax-778h]
0x14002846b  sub     rsp, 870h
0x140028472  mov     [rsp+870h+var_840], 0FFFFFFFFFFFFFFFEh
0x14002847b  mov     [rax+10h], rbx
0x14002847f  mov     [rax+18h], rdi
0x140028483  mov     rax, cs:__security_cookie
0x14002848a  xor     rax, rsp
0x14002848d  mov     [rbp+770h+var_10], rax
0x140028494  mov     ebx, ecx
0x140028496  mov     [rsp+870h+pperrinfo], 0
0x14002849f  lea     rcx, [rsp+870h+pperrinfo]; pperrinfo
0x1400284a4  call    cs:__imp_CreateErrorInfo
0x1400284aa  test    eax, eax
0x1400284ac  js      loc_140028537
0x1400284b2  mov     edx, ebx; dwMessageId
0x1400284b4  lea     rcx, [rsp+870h+var_830]; this
0x1400284b9  call    ??0CErrorString@@QEAA@JH@Z; CErrorString::CErrorString(long,int)
0x1400284be  nop
0x1400284bf  mov     rdi, [rsp+870h+pperrinfo]
0x1400284c4  mov     rax, [rdi]
0x1400284c7  mov     rbx, [rax+28h]
0x1400284cb  xor     edx, edx; int
0x1400284cd  lea     rcx, [rsp+870h+var_830]; this
0x1400284d2  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1400284d7  mov     rdx, rax
0x1400284da  mov     rcx, rdi
0x1400284dd  mov     rax, rbx
0x1400284e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400284e5  test    eax, eax
0x1400284e7  js      short loc_14002852B
0x1400284e9  mov     [rsp+870h+perrinfo], 0
0x1400284f2  mov     rcx, [rsp+870h+pperrinfo]
0x1400284f7  mov     rax, [rcx]
0x1400284fa  lea     r8, [rsp+870h+perrinfo]
0x1400284ff  lea     rdx, IID_IErrorInfo
0x140028506  mov     rax, [rax]
0x140028509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002850e  test    eax, eax
0x140028510  js      short loc_140028520
0x140028512  mov     rdx, [rsp+870h+perrinfo]; perrinfo
0x140028517  xor     ecx, ecx; dwReserved
0x140028519  call    cs:__imp_SetErrorInfo
0x14002851f  nop
0x140028520  lea     rcx, [rsp+870h+perrinfo]
0x140028525  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x14002852a  nop
0x14002852b  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x140028532  mov     [rsp+870h+var_830], rax
0x140028537  lea     rcx, [rsp+870h+pperrinfo]
0x14002853c  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x140028541  mov     rcx, [rbp+770h+var_10]
0x140028548  xor     rcx, rsp; StackCookie
0x14002854b  call    __security_check_cookie
0x140028550  lea     r11, [rsp+870h+var_s0]
0x140028558  mov     rbx, [r11+18h]
0x14002855c  mov     rdi, [r11+20h]
0x140028560  mov     rsp, r11
0x140028563  pop     rbp
0x140028564  retn
```
