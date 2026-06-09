# CServer::CreateObject(ushort *,IDispatch * *)

- ea: `0x180057330`
- end: `0x1800574da`
- name: `?CreateObject@CServer@@UEAAJPEAGPEAPEAUIDispatch@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(CServer *this, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180023d62`
- `0x180023dd0`
- `0x18003776c`
- `0x1800406b0`
- `0x180045f6c`
- `0x1800572f8`
- `0x180057330`
- `0x180060494`
- `0x180064010`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x18005741a`
- `ole32!CLSIDFromProgID` at `0x18005741a`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180057452`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180057452`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180057467`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180057467`

## pseudocode

```c
__int64 __fastcall CServer::CreateObject(CServer *this, unsigned __int16 *a2, struct IDispatch **a3)
{
  CTypelibCache *v6; // rcx
  HRESULT v8; // ebx
  int v9; // r9d
  unsigned int v10; // r8d
  int v11; // [rsp+30h] [rbp-30h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID Buf1; // [rsp+40h] [rbp-20h] BYREF

  if ( (int)CServer::CheckForTombstone(this) < 0 )
    return 2147500037LL;
  if ( !a2 )
  {
    ExceptionId(&IID_IServer, 0x1838u, 0x66u, 0);
    return 2147500037LL;
  }
  *a3 = 0;
  Buf1 = 0;
  if ( DWORD2(xmmword_180079F90) )
  {
    v8 = CTypelibCache::CreateComponent(v6, a2, *(struct CHitObj **)(*((_QWORD *)this + 6) + 48LL), a3, &Buf1);
    if ( v8 < 0 )
    {
      if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
        goto LABEL_8;
      goto LABEL_14;
    }
  }
  else
  {
    v8 = CLSIDFromProgID(a2, &Buf1);
    if ( v8 < 0 )
      goto LABEL_8;
    v8 = CHitObj::CreateComponent(*(CHitObj **)(*((_QWORD *)this + 6) + 48LL), &Buf1, a3);
    if ( v8 < 0 )
    {
LABEL_14:
      pperrinfo = 0;
      if ( !GetErrorInfo(0, &pperrinfo) && pperrinfo )
      {
        SetErrorInfo(0, pperrinfo);
        ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
        return (unsigned int)v8;
      }
      if ( v8 == -2147024891 )
      {
        v9 = 0;
        v10 = 6210;
        goto LABEL_9;
      }
      if ( v8 == -2147221164 )
      {
        v11 = 0;
        if ( (int)CompModelFromCLSID(&Buf1, 0, &v11) < 0 || v11 )
          return (unsigned int)v8;
        v9 = 0;
        v10 = 6211;
        goto LABEL_9;
      }
LABEL_8:
      v9 = v8;
      v10 = 6209;
LABEL_9:
      ExceptionId(&IID_IServer, 0x1838u, v10, v9);
      return (unsigned int)v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180057330  mov     [rsp-18h+arg_18], rbx
0x180057335  push    rbp
0x180057336  push    rsi
0x180057337  push    rdi
0x180057338  mov     rbp, rsp
0x18005733b  sub     rsp, 60h
0x18005733f  mov     rax, cs:__security_cookie
0x180057346  xor     rax, rsp
0x180057349  mov     [rbp+var_10], rax
0x18005734d  mov     rdi, r8
0x180057350  mov     rbx, rdx
0x180057353  mov     rsi, rcx
0x180057356  call    ?CheckForTombstone@CServer@@QEAAJXZ; CServer::CheckForTombstone(void)
0x18005735b  test    eax, eax
0x18005735d  jns     short loc_180057369
0x18005735f  mov     eax, 80004005h
0x180057364  jmp     loc_1800573F7
0x180057369  test    rbx, rbx
0x18005736c  jnz     short loc_180057388
0x18005736e  xor     r9d, r9d; int
0x180057371  lea     r8d, [rbx+66h]; unsigned int
0x180057375  mov     edx, 1838h; unsigned int
0x18005737a  lea     rcx, IID_IServer; struct _GUID *
0x180057381  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x180057386  jmp     short loc_18005735F
0x180057388  mov     qword ptr [rdi], 0
0x18005738f  xorps   xmm0, xmm0
0x180057392  cmp     dword ptr cs:xmmword_180079F90+8, 0
0x180057399  movups  [rbp+Buf1], xmm0
0x18005739d  jz      short loc_180057413
0x18005739f  mov     r8, [rsi+30h]
0x1800573a3  lea     rax, [rbp+Buf1]
0x1800573a7  mov     r9, rdi; struct IDispatch **
0x1800573aa  mov     [rsp+60h+var_40], rax; struct _GUID *
0x1800573af  mov     rdx, rbx; unsigned __int16 *
0x1800573b2  mov     r8, [r8+30h]; struct CHitObj *
0x1800573b6  call    ?CreateComponent@CTypelibCache@@QEAAJPEAGPEAVCHitObj@@PEAPEAUIDispatch@@PEAU_GUID@@@Z; CTypelibCache::CreateComponent(ushort *,CHitObj *,IDispatch * *,_GUID *)
0x1800573bb  mov     ebx, eax
0x1800573bd  test    eax, eax
0x1800573bf  jns     short loc_180057440
0x1800573c1  mov     r8d, 10h; Size
0x1800573c7  lea     rdx, GUID_NULL; Buf2
0x1800573ce  lea     rcx, [rbp+Buf1]; Buf1
0x1800573d2  call    memcmp_0
0x1800573d7  test    eax, eax
0x1800573d9  jnz     short loc_180057444
0x1800573db  mov     r9d, ebx; int
0x1800573de  mov     r8d, 1841h; unsigned int
0x1800573e4  mov     edx, 1838h; unsigned int
0x1800573e9  lea     rcx, IID_IServer; struct _GUID *
0x1800573f0  call    ?ExceptionId@@YAXAEBU_GUID@@IIJ@Z; ExceptionId(_GUID const &,uint,uint,long)
0x1800573f5  mov     eax, ebx
0x1800573f7  mov     rcx, [rbp+var_10]
0x1800573fb  xor     rcx, rsp; StackCookie
0x1800573fe  call    __security_check_cookie
0x180057403  mov     rbx, [rsp+60h+arg_18]
0x18005740b  add     rsp, 60h
0x18005740f  pop     rdi
0x180057410  pop     rsi
0x180057411  pop     rbp
0x180057412  retn
0x180057413  lea     rdx, [rbp+Buf1]; lpclsid
0x180057417  mov     rcx, rbx; lpszProgID
0x18005741a  call    cs:__imp_CLSIDFromProgID
0x180057420  mov     ebx, eax
0x180057422  test    eax, eax
0x180057424  js      short loc_1800573DB
0x180057426  mov     rcx, [rsi+30h]
0x18005742a  lea     rdx, [rbp+Buf1]; struct _GUID *
0x18005742e  mov     r8, rdi; struct IDispatch **
0x180057431  mov     rcx, [rcx+30h]; this
0x180057435  call    ?CreateComponent@CHitObj@@QEAAJAEBU_GUID@@PEAPEAUIDispatch@@@Z; CHitObj::CreateComponent(_GUID const &,IDispatch * *)
0x18005743a  mov     ebx, eax
0x18005743c  test    eax, eax
0x18005743e  js      short loc_180057444
0x180057440  xor     eax, eax
0x180057442  jmp     short loc_1800573F7
0x180057444  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180057448  mov     [rbp+pperrinfo], 0
0x180057450  xor     ecx, ecx; dwReserved
0x180057452  call    cs:__imp_GetErrorInfo
0x180057458  test    eax, eax
0x18005745a  jnz     short loc_180057482
0x18005745c  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180057460  test    rdx, rdx
0x180057463  jz      short loc_180057482
0x180057465  xor     ecx, ecx; dwReserved
0x180057467  call    cs:__imp_SetErrorInfo
0x18005746d  mov     rcx, [rbp+pperrinfo]
0x180057471  mov     rax, [rcx]
0x180057474  mov     rax, [rax+10h]
0x180057478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005747d  jmp     loc_1800573F5
0x180057482  cmp     ebx, 80070005h
0x180057488  jnz     short loc_180057498
0x18005748a  xor     r9d, r9d
0x18005748d  mov     r8d, 1842h
0x180057493  jmp     loc_1800573E4
0x180057498  cmp     ebx, 80040154h
0x18005749e  jnz     loc_1800573DB
0x1800574a4  lea     r8, [rbp+var_30]; int *
0x1800574a8  mov     [rbp+var_30], 0
0x1800574af  xor     edx, edx; unsigned int *
0x1800574b1  lea     rcx, [rbp+Buf1]; struct _GUID *
0x1800574b5  call    ?CompModelFromCLSID@@YAJAEBU_GUID@@PEAKPEAH@Z; CompModelFromCLSID(_GUID const &,ulong *,int *)
0x1800574ba  test    eax, eax
0x1800574bc  js      loc_1800573F5
0x1800574c2  cmp     [rbp+var_30], 0
0x1800574c6  jnz     loc_1800573F5
0x1800574cc  xor     r9d, r9d
0x1800574cf  mov     r8d, 1843h
0x1800574d5  jmp     loc_1800573E4
```
