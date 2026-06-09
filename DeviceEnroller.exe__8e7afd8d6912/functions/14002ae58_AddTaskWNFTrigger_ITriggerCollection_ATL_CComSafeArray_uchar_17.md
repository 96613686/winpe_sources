# AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)

- ea: `0x14002ae58`
- end: `0x14002afc8`
- name: `?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002aaa0`

## callees

- `0x14000e548`
- `0x14002ae58`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002af3e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002af3e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002af81`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002af81`
- `OLEAUT32!__imp_SafeArrayLock` at `0x14002af4f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x14002af4f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14002af74`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14002af74`

## pseudocode

```c
__int64 __fastcall AddTaskWNFTrigger(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // rax
  int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  SAFEARRAY *v11; // rax
  SAFEARRAY *v12; // rbx
  HRESULT v13; // eax
  unsigned int v14; // edi
  __int64 v15; // [rsp+40h] [rbp+20h] BYREF
  __int64 v16; // [rsp+50h] [rbp+30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp+38h] BYREF

  v2 = *a1;
  v16 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v2 + 80))(a1, 12, &v16);
  v5 = v16;
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( !v16 )
      return v6;
LABEL_3:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v5);
    return v6;
  }
  v15 = 0;
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v16)(v16, &IID_IWnfStateChangeTrigger, &v15);
  v9 = v15;
  v6 = v8;
  if ( v8 < 0
    || (v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 152LL))(v15, 0xFFFFFFFFLL),
        v9 = v15,
        v6 = v10,
        v10 < 0) )
  {
LABEL_6:
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v5 = v16;
    if ( !v16 )
      return v6;
    goto LABEL_3;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 184LL))(v15, *a2);
  if ( (v6 & 0x80000000) != 0 )
  {
    v9 = v15;
    goto LABEL_6;
  }
  rgsabound = 0;
  v11 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v12 = v11;
  if ( !v11 )
  {
    v13 = -2147024882;
LABEL_23:
    ATL::AtlThrowImpl(v13);
  }
  v13 = SafeArrayLock(v11);
  if ( v13 < 0 )
    goto LABEL_23;
  v14 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v15 + 200LL))(v15, v12);
  if ( SafeArrayUnlock(v12) >= 0 )
    SafeArrayDestroy(v12);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v14;
}

```

## disassembly

```asm
0x14002ae58  push    rbp
0x14002ae5a  push    rbx
0x14002ae5b  push    rdi
0x14002ae5c  mov     rbp, rsp
0x14002ae5f  sub     rsp, 20h
0x14002ae63  mov     rax, [rcx]
0x14002ae66  lea     r8, [rbp+arg_10]
0x14002ae6a  mov     rdi, rdx
0x14002ae6d  mov     [rbp+arg_10], 0
0x14002ae75  mov     edx, 0Ch
0x14002ae7a  mov     rax, [rax+50h]
0x14002ae7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae83  mov     rcx, [rbp+arg_10]
0x14002ae87  mov     ebx, eax
0x14002ae89  test    eax, eax
0x14002ae8b  jns     short loc_14002AEA5
0x14002ae8d  test    rcx, rcx
0x14002ae90  jz      short loc_14002AE9E
0x14002ae92  mov     rdx, [rcx]
0x14002ae95  mov     rax, [rdx+10h]
0x14002ae99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae9e  mov     eax, ebx
0x14002aea0  jmp     loc_14002AFB3
0x14002aea5  mov     [rbp+arg_0], 0
0x14002aead  lea     r8, [rbp+arg_0]
0x14002aeb1  mov     rax, [rcx]
0x14002aeb4  lea     rdx, IID_IWnfStateChangeTrigger
0x14002aebb  mov     rax, [rax]
0x14002aebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aec3  mov     rcx, [rbp+arg_0]
0x14002aec7  mov     ebx, eax
0x14002aec9  test    eax, eax
0x14002aecb  jns     short loc_14002AEF0
0x14002aecd  test    rcx, rcx
0x14002aed0  jz      short loc_14002AEDE
0x14002aed2  mov     rdx, [rcx]
0x14002aed5  mov     rax, [rdx+10h]
0x14002aed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aede  mov     rcx, [rbp+arg_10]
0x14002aee2  test    rcx, rcx
0x14002aee5  jz      short loc_14002AE9E
0x14002aee7  mov     rax, [rcx]
0x14002aeea  mov     rax, [rax+10h]
0x14002aeee  jmp     short loc_14002AE99
0x14002aef0  mov     rax, [rcx]
0x14002aef3  or      edx, 0FFFFFFFFh
0x14002aef6  mov     rax, [rax+98h]
0x14002aefd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af02  mov     rcx, [rbp+arg_0]
0x14002af06  mov     ebx, eax
0x14002af08  test    eax, eax
0x14002af0a  js      short loc_14002AECD
0x14002af0c  mov     rax, [rcx]
0x14002af0f  mov     rdx, [rdi]
0x14002af12  mov     rax, [rax+0B8h]
0x14002af19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af1e  mov     ebx, eax
0x14002af20  test    eax, eax
0x14002af22  jns     short loc_14002AF2A
0x14002af24  mov     rcx, [rbp+arg_0]
0x14002af28  jmp     short loc_14002AECD
0x14002af2a  mov     ecx, 11h; vt
0x14002af2f  mov     qword ptr [rbp+rgsabound.cElements], 0
0x14002af37  lea     r8, [rbp+rgsabound]; rgsabound
0x14002af3b  lea     edx, [rcx-10h]; cDims
0x14002af3e  call    cs:__imp_SafeArrayCreate
0x14002af44  mov     rbx, rax
0x14002af47  test    rax, rax
0x14002af4a  jz      short loc_14002AFBB
0x14002af4c  mov     rcx, rbx; psa
0x14002af4f  call    cs:__imp_SafeArrayLock
0x14002af55  test    eax, eax
0x14002af57  js      short loc_14002AFC0
0x14002af59  mov     rcx, [rbp+arg_0]
0x14002af5d  mov     rdx, rbx
0x14002af60  mov     rax, [rcx]
0x14002af63  mov     rax, [rax+0C8h]
0x14002af6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af6f  mov     rcx, rbx; psa
0x14002af72  mov     edi, eax
0x14002af74  call    cs:__imp_SafeArrayUnlock
0x14002af7a  test    eax, eax
0x14002af7c  js      short loc_14002AF87
0x14002af7e  mov     rcx, rbx; psa
0x14002af81  call    cs:__imp_SafeArrayDestroy
0x14002af87  mov     rcx, [rbp+arg_0]
0x14002af8b  test    rcx, rcx
0x14002af8e  jz      short loc_14002AF9C
0x14002af90  mov     rax, [rcx]
0x14002af93  mov     rax, [rax+10h]
0x14002af97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002af9c  mov     rcx, [rbp+arg_10]
0x14002afa0  test    rcx, rcx
0x14002afa3  jz      short loc_14002AFB1
0x14002afa5  mov     rax, [rcx]
0x14002afa8  mov     rax, [rax+10h]
0x14002afac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002afb1  mov     eax, edi
0x14002afb3  add     rsp, 20h
0x14002afb7  pop     rdi
0x14002afb8  pop     rbx
0x14002afb9  pop     rbp
0x14002afba  retn
0x14002afbb  mov     eax, 8007000Eh
0x14002afc0  mov     ecx, eax; int
0x14002afc2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
