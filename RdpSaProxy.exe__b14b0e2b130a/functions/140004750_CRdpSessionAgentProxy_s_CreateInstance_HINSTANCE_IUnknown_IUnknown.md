# CRdpSessionAgentProxy::s_CreateInstance(HINSTANCE__ *,IUnknown *,IUnknown * *)

- ea: `0x140004750`
- end: `0x140004994`
- name: `?s_CreateInstance@CRdpSessionAgentProxy@@SAJPEAUHINSTANCE__@@PEAUIUnknown@@PEAPEAU3@@Z`
- size: `580`
- prototype: `__int64 __fastcall(HINSTANCE, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x140001540`
- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x140003ef4`
- `0x140004750`
- `0x140006010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400048e3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400048f9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000498c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400048e3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400048f9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000498c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400047c4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400047c4`

## string_xrefs

- `0x1400047f9`: `CRdpSessionAgentProxy`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::s_CreateInstance(HINSTANCE a1, struct IUnknown *a2, struct IUnknown **a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v6; // edi
  _DWORD *v7; // rbx
  _DWORD *v8; // rax
  char *v9; // rax
  unsigned int v10; // eax
  struct CRdpSessionAgentProxy *v11; // rcx
  unsigned int v13; // eax

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147221232);
    }
    return (unsigned int)-2147221232;
  }
  v7 = 0;
  v6 = 0;
  AcquireSRWLockExclusive(&CRdpSessionAgentProxy::s_lockSingleton);
  if ( CRdpSessionAgentProxy::s_pSingleton )
    goto LABEL_16;
  v8 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v8;
  if ( v8 )
  {
    v8[10] = -607474739;
    *((_QWORD *)v8 + 4) = "CRdpSessionAgentProxy";
    v9 = (char *)(v8 + 4);
    *(_QWORD *)v9 = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v9 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
    *((_DWORD *)v9 + 7) = 1;
    *((_DWORD *)v9 + 10) = 0;
    *((_QWORD *)v9 + 4) = v9;
    *(_QWORD *)v7 = &CRdpSessionAgentProxy::`vftable'{for `IRdpSessionAgent'};
    *((_QWORD *)v7 + 1) = &CRdpSessionAgentProxy::`vftable'{for `IRdpSessionAgentProxy'};
    *(_QWORD *)v9 = &CRdpSessionAgentProxy::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v7 + 3) = &CRdpSessionAgentProxy::`vftable'{for `CTSObject'};
    *((_QWORD *)v7 + 8) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[20] = 0;
    *((_QWORD *)v7 + 11) = 0;
    *((_QWORD *)v7 + 12) = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 6) + 8LL))(*((_QWORD *)v7 + 6));
    v6 = CRdpSessionAgentProxy::Initialize((CRdpSessionAgentProxy *)v7, a1);
    if ( (v6 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
          v10,
          (__int64)"spNewObject->Initialize failed!",
          v6);
      }
      ReleaseSRWLockExclusive(&CRdpSessionAgentProxy::s_lockSingleton);
      goto LABEL_17;
    }
    CRdpSessionAgentProxy::s_pSingleton = (struct CRdpSessionAgentProxy *)v7;
LABEL_16:
    ReleaseSRWLockExclusive(&CRdpSessionAgentProxy::s_lockSingleton);
    v11 = CRdpSessionAgentProxy::s_pSingleton;
    *a3 = (struct IUnknown *)CRdpSessionAgentProxy::s_pSingleton;
    (*(void (__fastcall **)(struct CRdpSessionAgentProxy *))(*(_QWORD *)v11 + 8LL))(v11);
    if ( !v7 )
      return v6;
LABEL_17:
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 6) + 16LL))(*((_QWORD *)v7 + 6));
    return v6;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
      v13,
      -2147024882);
  }
  v6 = -2147024882;
  ReleaseSRWLockExclusive(&CRdpSessionAgentProxy::s_lockSingleton);
  return v6;
}

```

## disassembly

```asm
0x140004750  push    rbx
0x140004752  push    rbp
0x140004753  push    rsi
0x140004754  push    rdi
0x140004755  sub     rsp, 38h
0x140004759  mov     rsi, r8
0x14000475c  mov     rbp, rcx
0x14000475f  test    rdx, rdx
0x140004762  jz      short loc_1400047B9
0x140004764  mov     rcx, cs:WPP_GLOBAL_Control
0x14000476b  lea     rax, WPP_GLOBAL_Control
0x140004772  cmp     rcx, rax
0x140004775  jz      short loc_1400047AF
0x140004777  test    byte ptr [rcx+1Ch], 8
0x14000477b  jz      short loc_1400047AF
0x14000477d  cmp     byte ptr [rcx+19h], 2
0x140004781  jb      short loc_1400047AF
0x140004783  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004788  mov     rcx, cs:WPP_GLOBAL_Control
0x14000478f  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140004796  mov     edx, 10h
0x14000479b  mov     dword ptr [rsp+58h+var_38], 80040110h
0x1400047a3  mov     r9d, eax
0x1400047a6  mov     rcx, [rcx+10h]
0x1400047aa  call    WPP_SF_Dd
0x1400047af  mov     edi, 80040110h
0x1400047b4  jmp     loc_14000492A
0x1400047b9  lea     rcx, ?s_lockSingleton@CRdpSessionAgentProxy@@0VSlimRWLock@@A; SRWLock
0x1400047c0  xor     ebx, ebx
0x1400047c2  xor     edi, edi
0x1400047c4  call    cs:__imp_AcquireSRWLockExclusive
0x1400047ca  cmp     cs:?s_pSingleton@CRdpSessionAgentProxy@@0PEAV1@EA, rbx; CRdpSessionAgentProxy * CRdpSessionAgentProxy::s_pSingleton
0x1400047d1  jnz     loc_1400048F2
0x1400047d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400047de  lea     ecx, [rbx+68h]; unsigned __int64
0x1400047e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400047e6  mov     rbx, rax
0x1400047e9  test    rax, rax
0x1400047ec  jz      loc_140004935
0x1400047f2  mov     dword ptr [rax+28h], 0DBCAABCDh
0x1400047f9  lea     rcx, aCrdpsessionage; "CRdpSessionAgentProxy"
0x140004800  mov     [rax+20h], rcx
0x140004804  add     rax, 10h
0x140004808  lea     rcx, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x14000480f  mov     [rax], rcx
0x140004812  lea     rcx, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x140004819  mov     [rax+8], rcx
0x14000481d  lea     rcx, ??_7CRdpSessionAgentProxy@@6BIRdpSessionAgent@@@; const CRdpSessionAgentProxy::`vftable'{for `IRdpSessionAgent'}
0x140004824  mov     dword ptr [rax+1Ch], 1
0x14000482b  mov     [rax+28h], edi
0x14000482e  mov     [rax+20h], rax
0x140004832  mov     [rbx], rcx
0x140004835  lea     rcx, ??_7CRdpSessionAgentProxy@@6BIRdpSessionAgentProxy@@@; const CRdpSessionAgentProxy::`vftable'{for `IRdpSessionAgentProxy'}
0x14000483c  mov     [rbx+8], rcx
0x140004840  lea     rcx, ??_7CRdpSessionAgentProxy@@6BINonDelegatingUnknown@@@; const CRdpSessionAgentProxy::`vftable'{for `INonDelegatingUnknown'}
0x140004847  mov     [rax], rcx
0x14000484a  lea     rax, ??_7CRdpSessionAgentProxy@@6BCTSObject@@@; const CRdpSessionAgentProxy::`vftable'{for `CTSObject'}
0x140004851  mov     [rbx+18h], rax
0x140004855  mov     [rbx+40h], rdi
0x140004859  mov     [rbx+48h], rdi
0x14000485d  mov     [rbx+50h], edi
0x140004860  mov     [rbx+58h], rdi
0x140004864  mov     [rbx+60h], rdi
0x140004868  mov     rcx, [rbx+30h]
0x14000486c  mov     rax, [rcx]
0x14000486f  mov     rax, [rax+8]
0x140004873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004878  mov     rdx, rbp; HINSTANCE
0x14000487b  mov     rcx, rbx; this
0x14000487e  call    ?Initialize@CRdpSessionAgentProxy@@QEAAJPEAUHINSTANCE__@@@Z; CRdpSessionAgentProxy::Initialize(HINSTANCE__ *)
0x140004883  mov     edi, eax
0x140004885  test    eax, eax
0x140004887  jns     short loc_1400048EB
0x140004889  mov     rcx, cs:WPP_GLOBAL_Control
0x140004890  lea     rax, WPP_GLOBAL_Control
0x140004897  cmp     rcx, rax
0x14000489a  jz      short loc_1400048DC
0x14000489c  test    byte ptr [rcx+1Ch], 8
0x1400048a0  jz      short loc_1400048DC
0x1400048a2  cmp     byte ptr [rcx+19h], 2
0x1400048a6  jb      short loc_1400048DC
0x1400048a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400048ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048b4  lea     r8, aSpnewobjectIni; "spNewObject->Initialize failed!"
0x1400048bb  mov     [rsp+58h+var_30], edi
0x1400048bf  mov     edx, 12h
0x1400048c4  mov     [rsp+58h+var_38], r8
0x1400048c9  mov     r9d, eax
0x1400048cc  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x1400048d3  mov     rcx, [rcx+10h]
0x1400048d7  call    WPP_SF_DsD
0x1400048dc  lea     rcx, ?s_lockSingleton@CRdpSessionAgentProxy@@0VSlimRWLock@@A; SRWLock
0x1400048e3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400048e9  jmp     short loc_14000491A
0x1400048eb  mov     cs:?s_pSingleton@CRdpSessionAgentProxy@@0PEAV1@EA, rbx; CRdpSessionAgentProxy * CRdpSessionAgentProxy::s_pSingleton
0x1400048f2  lea     rcx, ?s_lockSingleton@CRdpSessionAgentProxy@@0VSlimRWLock@@A; SRWLock
0x1400048f9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400048ff  mov     rcx, cs:?s_pSingleton@CRdpSessionAgentProxy@@0PEAV1@EA; CRdpSessionAgentProxy * CRdpSessionAgentProxy::s_pSingleton
0x140004906  mov     [rsi], rcx
0x140004909  mov     rax, [rcx]
0x14000490c  mov     rax, [rax+8]
0x140004910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004915  test    rbx, rbx
0x140004918  jz      short loc_14000492A
0x14000491a  mov     rcx, [rbx+30h]
0x14000491e  mov     rax, [rcx]
0x140004921  mov     rax, [rax+10h]
0x140004925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000492a  mov     eax, edi
0x14000492c  add     rsp, 38h
0x140004930  pop     rdi
0x140004931  pop     rsi
0x140004932  pop     rbp
0x140004933  pop     rbx
0x140004934  retn
0x140004935  mov     rcx, cs:WPP_GLOBAL_Control
0x14000493c  lea     rax, WPP_GLOBAL_Control
0x140004943  cmp     rcx, rax
0x140004946  jz      short loc_140004980
0x140004948  test    byte ptr [rcx+1Ch], 8
0x14000494c  jz      short loc_140004980
0x14000494e  cmp     byte ptr [rcx+19h], 2
0x140004952  jb      short loc_140004980
0x140004954  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004959  mov     rcx, cs:WPP_GLOBAL_Control
0x140004960  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140004967  mov     edx, 11h
0x14000496c  mov     dword ptr [rsp+58h+var_38], 8007000Eh
0x140004974  mov     r9d, eax
0x140004977  mov     rcx, [rcx+10h]
0x14000497b  call    WPP_SF_Dd
0x140004980  lea     rcx, ?s_lockSingleton@CRdpSessionAgentProxy@@0VSlimRWLock@@A; SRWLock
0x140004987  mov     edi, 8007000Eh
0x14000498c  call    cs:__imp_ReleaseSRWLockExclusive
0x140004992  jmp     short loc_14000492A
```
