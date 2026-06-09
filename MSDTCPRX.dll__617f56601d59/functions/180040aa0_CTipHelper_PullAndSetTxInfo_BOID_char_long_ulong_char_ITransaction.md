# CTipHelper::PullAndSetTxInfo(BOID *,char *,long,ulong,char *,ITransaction * *)

- ea: `0x180040aa0`
- end: `0x180040c8f`
- name: `?PullAndSetTxInfo@CTipHelper@@QEAAJPEAUBOID@@PEADJK1PEAPEAUITransaction@@@Z`
- size: `495`
- prototype: `__int64 __usercall@<rax>(CTipHelper *__hidden this@<rcx>, UUID *Uuid@<rdx>, char *@<r8>, int@<r9d>, unsigned int, char *, struct ITransaction **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800380c0`

## callees

- `0x18000e3bc`
- `0x18002183c`
- `0x180024674`
- `0x18002b60c`
- `0x180040670`
- `0x180040aa0`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040c48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040c48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040baa`
- `RPCRT4!RpcStringFreeA` at `0x180040c5b`
- `RPCRT4!RpcStringFreeA` at `0x180040c5b`
- `RPCRT4!UuidToStringA` at `0x180040b6d`
- `RPCRT4!UuidToStringA` at `0x180040b6d`

## pseudocode

```c
__int64 __fastcall CTipHelper::PullAndSetTxInfo(
        CTipHelper *this,
        UUID *Uuid,
        char *a3,
        unsigned int a4,
        unsigned int a5,
        char *a6,
        struct ITransaction **a7)
{
  struct CTmProxyCore *v8; // rcx
  bool v11; // zf
  struct ITransaction *Instance; // rdi
  int v14; // ebx
  char *v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbp
  RPC_CSTR StringUuid; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-70h]
  struct _GUID v21; // [rsp+40h] [rbp-68h] BYREF

  v8 = (struct CTmProxyCore *)*((_QWORD *)this + 1);
  StringUuid = 0;
  v21 = 0;
  v11 = *((_QWORD *)v8 + 439) == 0;
  v20 = a4;
  if ( v11 || CTmProxyCore::GetTmVersion(v8) == 1 )
    return 2147799055LL;
  if ( !(unsigned int)CTmProxyCore::GetTipEnabled(*((CTmProxyCore **)this + 1)) )
    return 2147799075LL;
  if ( !Uuid || !a6 || !a7 )
    return 2147500035LL;
  *a7 = 0;
  Instance = (struct ITransaction *)CITransaction::CreateInstance(*((struct CTmProxyCore **)this + 1), 0);
  if ( Instance )
  {
    if ( UuidToStringA(Uuid, &StringUuid) )
    {
      v15 = 0;
    }
    else
    {
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( StringUuid[v17] );
      do
        ++v16;
      while ( a6[v16] );
      v18 = v16 + v17;
      v15 = (char *)CoTaskMemAlloc(v16 + v17 + 8);
      if ( v15 )
      {
        TracedStringCchPrintfA(v15, v18 + 8, "%s?OleTx-%s", a6, (const char *)StringUuid);
        v14 = CTipHelper::PerformTipPull(this, v15, 0, &v21);
        if ( v14 >= 0 )
        {
          v14 = ((__int64 (__fastcall *)(struct ITransaction *, UUID *, char *, _QWORD, unsigned int))Instance->lpVtbl[3].Release)(
                  Instance,
                  Uuid,
                  a3,
                  v20,
                  a5);
          if ( !v14 )
          {
            *a7 = Instance;
            ((void (__fastcall *)(struct ITransaction *))Instance->lpVtbl->AddRef)(Instance);
          }
        }
        goto LABEL_20;
      }
    }
    v14 = -2147024882;
LABEL_20:
    ((void (__fastcall *)(struct ITransaction *))Instance->lpVtbl->Release)(Instance);
    if ( v15 )
      CoTaskMemFree(v15);
    goto LABEL_22;
  }
  v14 = -2147024882;
LABEL_22:
  if ( StringUuid )
    RpcStringFreeA(&StringUuid);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180040aa0  push    rbx
0x180040aa2  push    rbp
0x180040aa3  push    rsi
0x180040aa4  push    rdi
0x180040aa5  push    r12
0x180040aa7  push    r13
0x180040aa9  push    r14
0x180040aab  push    r15
0x180040aad  sub     rsp, 68h
0x180040ab1  mov     rax, cs:__security_cookie
0x180040ab8  xor     rax, rsp
0x180040abb  mov     [rsp+0A8h+var_58], rax
0x180040ac0  mov     r12, [rsp+0A8h+arg_28]
0x180040ac8  mov     rbx, rcx
0x180040acb  mov     rcx, [rcx+8]; struct CTmProxyCore *
0x180040acf  xorps   xmm0, xmm0
0x180040ad2  mov     r14, [rsp+0A8h+arg_30]
0x180040ada  mov     r13, r8
0x180040add  mov     [rsp+0A8h+StringUuid], 0
0x180040ae6  mov     r15, rdx
0x180040ae9  movups  xmmword ptr [rsp+0A8h+var_68.Data1], xmm0
0x180040aee  cmp     qword ptr [rcx+0DB8h], 0
0x180040af6  mov     [rsp+0A8h+var_70], r9d
0x180040afb  jz      loc_180040C6C
0x180040b01  call    ?GetTmVersion@CTmProxyCore@@SAKPEAV1@@Z; CTmProxyCore::GetTmVersion(CTmProxyCore *)
0x180040b06  cmp     eax, 1
0x180040b09  jz      loc_180040C6C
0x180040b0f  mov     rcx, [rbx+8]; this
0x180040b13  call    ?GetTipEnabled@CTmProxyCore@@QEAAHXZ; CTmProxyCore::GetTipEnabled(void)
0x180040b18  test    eax, eax
0x180040b1a  jnz     short loc_180040B26
0x180040b1c  mov     eax, 8004D023h
0x180040b21  jmp     loc_180040C71
0x180040b26  test    r15, r15
0x180040b29  jz      loc_180040C65
0x180040b2f  test    r12, r12
0x180040b32  jz      loc_180040C65
0x180040b38  test    r14, r14
0x180040b3b  jz      loc_180040C65
0x180040b41  mov     qword ptr [r14], 0
0x180040b48  xor     edx, edx; int
0x180040b4a  mov     rcx, [rbx+8]; struct CTmProxyCore *
0x180040b4e  call    ?CreateInstance@CITransaction@@SAPEAUIDtcTxInit@@PEAVCTmProxyCore@@H@Z; CITransaction::CreateInstance(CTmProxyCore *,int)
0x180040b53  mov     rdi, rax
0x180040b56  test    rax, rax
0x180040b59  jnz     short loc_180040B65
0x180040b5b  mov     ebx, 8007000Eh
0x180040b60  jmp     loc_180040C4E
0x180040b65  lea     rdx, [rsp+0A8h+StringUuid]; StringUuid
0x180040b6a  mov     rcx, r15; Uuid
0x180040b6d  call    cs:__imp_UuidToStringA
0x180040b73  test    eax, eax
0x180040b75  jz      short loc_180040B83
0x180040b77  xor     esi, esi
0x180040b79  mov     ebx, 8007000Eh
0x180040b7e  jmp     loc_180040C31
0x180040b83  mov     rdx, [rsp+0A8h+StringUuid]
0x180040b88  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040b8c  mov     rcx, rax
0x180040b8f  inc     rcx
0x180040b92  cmp     byte ptr [rdx+rcx], 0
0x180040b96  jnz     short loc_180040B8F
0x180040b98  inc     rax
0x180040b9b  cmp     byte ptr [r12+rax], 0
0x180040ba0  jnz     short loc_180040B98
0x180040ba2  lea     rbp, [rax+rcx]
0x180040ba6  lea     rcx, [rbp+8]; cb
0x180040baa  call    cs:__imp_CoTaskMemAlloc
0x180040bb0  mov     rsi, rax
0x180040bb3  test    rax, rax
0x180040bb6  jz      short loc_180040B79
0x180040bb8  mov     rax, [rsp+0A8h+StringUuid]
0x180040bbd  lea     r8, aSOletxS; "%s?OleTx-%s"
0x180040bc4  mov     r9, r12
0x180040bc7  mov     [rsp+0A8h+var_88], rax
0x180040bcc  lea     rdx, [rbp+8]; unsigned __int64
0x180040bd0  mov     rcx, rsi; char *
0x180040bd3  call    ?TracedStringCchPrintfA@@YAXPEAD_KPEBDZZ; TracedStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180040bd8  lea     r9, [rsp+0A8h+var_68]; struct _GUID *
0x180040bdd  xor     r8d, r8d; struct ITipPullSink *
0x180040be0  mov     rdx, rsi; char *
0x180040be3  mov     rcx, rbx; this
0x180040be6  call    ?PerformTipPull@CTipHelper@@AEAAJPEADPEAUITipPullSink@@PEAU_GUID@@@Z; CTipHelper::PerformTipPull(char *,ITipPullSink *,_GUID *)
0x180040beb  mov     ebx, eax
0x180040bed  test    eax, eax
0x180040bef  js      short loc_180040C31
0x180040bf1  mov     rax, [rdi]
0x180040bf4  mov     r8, r13
0x180040bf7  mov     ecx, [rsp+0A8h+arg_20]
0x180040bfe  mov     rdx, r15
0x180040c01  mov     r9d, [rsp+0A8h+var_70]
0x180040c06  mov     dword ptr [rsp+0A8h+var_88], ecx
0x180040c0a  mov     rcx, rdi
0x180040c0d  mov     rax, [rax+0A0h]
0x180040c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c19  mov     ebx, eax
0x180040c1b  test    eax, eax
0x180040c1d  jnz     short loc_180040C31
0x180040c1f  mov     [r14], rdi
0x180040c22  mov     rcx, rdi
0x180040c25  mov     rax, [rdi]
0x180040c28  mov     rax, [rax+8]
0x180040c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c31  mov     rax, [rdi]
0x180040c34  mov     rcx, rdi
0x180040c37  mov     rax, [rax+10h]
0x180040c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c40  test    rsi, rsi
0x180040c43  jz      short loc_180040C4E
0x180040c45  mov     rcx, rsi; pv
0x180040c48  call    cs:__imp_CoTaskMemFree
0x180040c4e  cmp     [rsp+0A8h+StringUuid], 0
0x180040c54  jz      short loc_180040C61
0x180040c56  lea     rcx, [rsp+0A8h+StringUuid]; String
0x180040c5b  call    cs:__imp_RpcStringFreeA
0x180040c61  mov     eax, ebx
0x180040c63  jmp     short loc_180040C71
0x180040c65  mov     eax, 80004003h
0x180040c6a  jmp     short loc_180040C71
0x180040c6c  mov     eax, 8004D00Fh
0x180040c71  mov     rcx, [rsp+0A8h+var_58]
0x180040c76  xor     rcx, rsp; StackCookie
0x180040c79  call    __security_check_cookie
0x180040c7e  add     rsp, 68h
0x180040c82  pop     r15
0x180040c84  pop     r14
0x180040c86  pop     r13
0x180040c88  pop     r12
0x180040c8a  pop     rdi
0x180040c8b  pop     rsi
0x180040c8c  pop     rbp
0x180040c8d  pop     rbx
0x180040c8e  retn
```
