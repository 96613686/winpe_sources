# CSyncServices::CreateSyncSessionState(ISyncCallback *,ISyncSessionState * *)

- ea: `0x18002c800`
- end: `0x18002c957`
- name: `?CreateSyncSessionState@CSyncServices@@UEAAJPEAUISyncCallback@@PEAPEAUISyncSessionState@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(struct IdParameters **this, struct ISyncCallback *, struct ISyncSessionState **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002c800`
- `0x18002d520`
- `0x18002d6e0`
- `0x180030ef4`
- `0x180031130`
- `0x180094010`

## string_xrefs

- `0x18002c837`: `CSyncServices::CreateSyncSessionState`
- `0x18002c92e`: `CSyncServices::CreateSyncSessionState`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateSyncSessionState(
        struct IdParameters **this,
        struct ISyncCallback *a2,
        struct ISyncSessionState **a3)
{
  PVOID *v6; // rcx
  int v7; // ebx
  CSyncSessionStateData *v8; // rax
  CSyncSessionStateData *v9; // rax
  struct CSyncSessionStateData *v10; // rsi
  CSyncSessionState *v11; // rdi
  CSyncSessionState *v12; // rax
  CSyncSessionState *v13; // rax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateSyncSessionState");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    v8 = (CSyncSessionStateData *)SeAlloc(0x68u);
    if ( !v8 || (v9 = CSyncSessionStateData::CSyncSessionStateData(v8), (v10 = v9) == 0) )
    {
      v7 = -2147024882;
LABEL_20:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    if ( a2 )
    {
      v7 = CSyncSessionStateData::RegisterCallback(v9, a2);
      if ( v7 < 0 )
      {
        v11 = 0;
        goto LABEL_17;
      }
    }
    v12 = (CSyncSessionState *)SeAlloc(0x30u);
    if ( v12 )
    {
      v13 = CSyncSessionState::CSyncSessionState(v12, this[5], v10);
      v11 = v13;
      if ( v13 )
      {
        v7 = (**(__int64 (__fastcall ***)(CSyncSessionState *, GUID *, struct ISyncSessionState **))v13)(
               v13,
               &GUID_b8a940fe_9f01_483b_9434_c37d361225d9,
               a3);
        goto LABEL_17;
      }
    }
    else
    {
      v11 = 0;
    }
    v7 = -2147024882;
LABEL_17:
    CSyncSessionStateData::Release(v10);
    if ( v11 )
      (*(void (__fastcall **)(CSyncSessionState *))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_20;
  }
  v7 = -2147467261;
LABEL_21:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      61,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateSyncSessionState",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002c800  push    rbx
0x18002c802  push    rbp
0x18002c803  push    rsi
0x18002c804  push    rdi
0x18002c805  push    r14
0x18002c807  sub     rsp, 30h
0x18002c80b  mov     rbp, r8
0x18002c80e  mov     rbx, rdx
0x18002c811  mov     rdi, rcx
0x18002c814  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c81b  lea     r14, WPP_GLOBAL_Control
0x18002c822  cmp     rcx, r14
0x18002c825  jz      short loc_18002C856
0x18002c827  test    byte ptr [rcx+1Ch], 2
0x18002c82b  jz      short loc_18002C856
0x18002c82d  cmp     byte ptr [rcx+19h], 5
0x18002c831  jb      short loc_18002C856
0x18002c833  mov     rcx, [rcx+10h]
0x18002c837  lea     r9, aCsyncservicesC_5; "CSyncServices::CreateSyncSessionState"
0x18002c83e  mov     edx, 3Ch ; '<'
0x18002c843  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c84a  call    WPP_SF_s
0x18002c84f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c856  test    rbp, rbp
0x18002c859  jnz     short loc_18002C865
0x18002c85b  mov     ebx, 80004003h
0x18002c860  jmp     loc_18002C919
0x18002c865  mov     ecx, 68h ; 'h'; unsigned __int64
0x18002c86a  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002c86f  test    rax, rax
0x18002c872  jz      loc_18002C90D
0x18002c878  mov     rcx, rax; this
0x18002c87b  call    ??0CSyncSessionStateData@@QEAA@XZ; CSyncSessionStateData::CSyncSessionStateData(void)
0x18002c880  mov     rsi, rax
0x18002c883  test    rax, rax
0x18002c886  jz      loc_18002C90D
0x18002c88c  test    rbx, rbx
0x18002c88f  jz      short loc_18002C8A6
0x18002c891  mov     rdx, rbx; struct ISyncCallback *
0x18002c894  mov     rcx, rax; this
0x18002c897  call    ?RegisterCallback@CSyncSessionStateData@@QEAAJPEAUISyncCallback@@@Z; CSyncSessionStateData::RegisterCallback(ISyncCallback *)
0x18002c89c  mov     ebx, eax
0x18002c89e  test    eax, eax
0x18002c8a0  jns     short loc_18002C8A6
0x18002c8a2  xor     edi, edi
0x18002c8a4  jmp     short loc_18002C8EF
0x18002c8a6  mov     ecx, 30h ; '0'; unsigned __int64
0x18002c8ab  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002c8b0  test    rax, rax
0x18002c8b3  jz      short loc_18002C8E8
0x18002c8b5  mov     rdx, [rdi+28h]; struct IdParameters *
0x18002c8b9  mov     r8, rsi; struct CSyncSessionStateData *
0x18002c8bc  mov     rcx, rax; this
0x18002c8bf  call    ??0CSyncSessionState@@QEAA@PEAVIdParameters@@PEAVCSyncSessionStateData@@@Z; CSyncSessionState::CSyncSessionState(IdParameters *,CSyncSessionStateData *)
0x18002c8c4  mov     rdi, rax
0x18002c8c7  test    rax, rax
0x18002c8ca  jz      short loc_18002C8EA
0x18002c8cc  mov     rax, [rax]
0x18002c8cf  lea     rdx, _GUID_b8a940fe_9f01_483b_9434_c37d361225d9
0x18002c8d6  mov     r8, rbp
0x18002c8d9  mov     rcx, rdi
0x18002c8dc  mov     rax, [rax]
0x18002c8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8e4  mov     ebx, eax
0x18002c8e6  jmp     short loc_18002C8EF
0x18002c8e8  xor     edi, edi
0x18002c8ea  mov     ebx, 8007000Eh
0x18002c8ef  mov     rcx, rsi; this
0x18002c8f2  call    ?Release@CSyncSessionStateData@@QEAAKXZ; CSyncSessionStateData::Release(void)
0x18002c8f7  test    rdi, rdi
0x18002c8fa  jz      short loc_18002C912
0x18002c8fc  mov     rax, [rdi]
0x18002c8ff  mov     rcx, rdi
0x18002c902  mov     rax, [rax+10h]
0x18002c906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c90b  jmp     short loc_18002C912
0x18002c90d  mov     ebx, 8007000Eh
0x18002c912  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c919  cmp     rcx, r14
0x18002c91c  jz      short loc_18002C94A
0x18002c91e  test    byte ptr [rcx+1Ch], 2
0x18002c922  jz      short loc_18002C94A
0x18002c924  cmp     byte ptr [rcx+19h], 5
0x18002c928  jb      short loc_18002C94A
0x18002c92a  mov     rcx, [rcx+10h]
0x18002c92e  lea     r9, aCsyncservicesC_5; "CSyncServices::CreateSyncSessionState"
0x18002c935  mov     edx, 3Dh ; '='
0x18002c93a  mov     [rsp+58h+var_38], ebx
0x18002c93e  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c945  call    WPP_SF_sD
0x18002c94a  mov     eax, ebx
0x18002c94c  add     rsp, 30h
0x18002c950  pop     r14
0x18002c952  pop     rdi
0x18002c953  pop     rsi
0x18002c954  pop     rbp
0x18002c955  pop     rbx
0x18002c956  retn
```
