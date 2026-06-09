# AddNgcTaskTriggers(ATL::CComPtr<ITriggerCollection> &)

- ea: `0x14002aaa0`
- end: `0x14002ad04`
- name: `?AddNgcTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(struct ITriggerCollection **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140058c90`

## callees

- `0x1400042f0`
- `0x14000e548`
- `0x14001ea48`
- `0x14001ef20`
- `0x140028824`
- `0x14002aaa0`
- `0x14002ad0c`
- `0x14002ae58`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ab72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ab72`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002aaf3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002aaf3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002acc8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002acc8`
- `OLEAUT32!__imp_SafeArrayLock` at `0x14002ab0d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x14002ab0d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14002acbb`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x14002acbb`
- `SspiCli!GetUserNameExW` at `0x14002ab68`
- `SspiCli!GetUserNameExW` at `0x14002ab68`

## pseudocode

```c
__int64 __fastcall AddNgcTaskTriggers(struct ITriggerCollection **a1)
{
  SAFEARRAY *v2; // rax
  SAFEARRAY *v3; // rbx
  HRESULT v4; // eax
  unsigned int i; // edi
  signed int v6; // edi
  signed int LastError; // eax
  struct ITriggerCollection *v8; // rcx
  int v9; // eax
  SAFEARRAYBOUND v10; // rcx
  SAFEARRAY *v11; // rcx
  SAFEARRAY *v12; // rdi
  __int64 (__fastcall *v13)(SAFEARRAY *); // r14
  int v14; // eax
  SAFEARRAY *v16; // [rsp+20h] [rbp-E0h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-D8h] BYREF
  ULONG nSize; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR NameBuffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v19 = WNF_NGC_GESTURE_AUTHENTICATED;
  rgsabound = (SAFEARRAYBOUND)8LL;
  v2 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v16 = v2;
  v3 = v2;
  if ( !v2 )
  {
    v4 = -2147024882;
LABEL_29:
    ATL::AtlThrowImpl(v4);
  }
  v4 = SafeArrayLock(v2);
  if ( v4 < 0 )
    goto LABEL_29;
  for ( i = 0; i < 8; ++i )
    ATL::CComSafeArray<unsigned char,17>::SetAt(&v16, i, (char *)&NameBuffer[-4] + i);
  v6 = AddTaskWNFTrigger(*a1, &v16);
  if ( v6 < 0 )
    goto LABEL_24;
  nSize = 260;
  if ( !GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_24;
  }
  v8 = *a1;
  rgsabound = 0;
  v9 = ((__int64 (__fastcall *)(struct ITriggerCollection *, __int64, SAFEARRAYBOUND *))v8->lpVtbl->Create)(
         v8,
         9,
         &rgsabound);
  v10 = rgsabound;
  v6 = v9;
  if ( v9 < 0 )
    goto LABEL_17;
  v16 = 0;
  v6 = (***(__int64 (__fastcall ****)(SAFEARRAYBOUND, GUID *, SAFEARRAY **))&rgsabound)(
         rgsabound,
         &IID_ILogonTrigger,
         &v16);
  if ( v6 < 0 )
  {
    v11 = v16;
LABEL_14:
    if ( v11 )
      (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&v11->cDims + 16LL))(v11);
    v10 = rgsabound;
LABEL_17:
    if ( v10 )
      (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v10 + 16LL))(v10);
    goto LABEL_24;
  }
  v12 = v16;
  v13 = *(__int64 (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&v16->cDims + 184LL);
  _bstr_t::_bstr_t((_bstr_t *)&v19, NameBuffer);
  v6 = v13(v12);
  _bstr_t::~_bstr_t((_bstr_t *)&v19);
  v11 = v16;
  if ( v6 < 0 )
    goto LABEL_14;
  v14 = (*(__int64 (__fastcall **)(SAFEARRAY *, __int64))(*(_QWORD *)&v16->cDims + 152LL))(v16, 0xFFFFFFFFLL);
  v11 = v16;
  v6 = v14;
  if ( v14 < 0 )
    goto LABEL_14;
  if ( v16 )
    (*(void (**)(void))(*(_QWORD *)&v16->cDims + 16LL))();
  if ( rgsabound )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
  v6 = AddTaskUnlockTrigger(*a1, NameBuffer);
LABEL_24:
  if ( v3 && SafeArrayUnlock(v3) >= 0 )
    SafeArrayDestroy(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002aaa0  mov     [rsp-8+arg_8], rbx
0x14002aaa5  mov     [rsp-8+arg_10], rsi
0x14002aaaa  push    rbp
0x14002aaab  push    rdi
0x14002aaac  push    r14
0x14002aaae  lea     rbp, [rsp-160h]
0x14002aab6  sub     rsp, 260h
0x14002aabd  mov     rax, cs:__security_cookie
0x14002aac4  xor     rax, rsp
0x14002aac7  mov     [rbp+170h+var_20], rax
0x14002aace  mov     rax, cs:WNF_NGC_GESTURE_AUTHENTICATED
0x14002aad5  lea     r8, [rsp+270h+rgsabound]; rgsabound
0x14002aada  mov     rsi, rcx
0x14002aadd  mov     [rsp+270h+var_238], rax
0x14002aae2  mov     ecx, 11h; vt
0x14002aae7  mov     qword ptr [rsp+270h+rgsabound.cElements], 8
0x14002aaf0  lea     edx, [rcx-10h]; cDims
0x14002aaf3  call    cs:__imp_SafeArrayCreate
0x14002aaf9  mov     [rsp+270h+var_250], rax
0x14002aafe  mov     rbx, rax
0x14002ab01  test    rax, rax
0x14002ab04  jz      loc_14002ACF7
0x14002ab0a  mov     rcx, rbx; psa
0x14002ab0d  call    cs:__imp_SafeArrayLock
0x14002ab13  test    eax, eax
0x14002ab15  js      loc_14002ACFC
0x14002ab1b  xor     edi, edi
0x14002ab1d  mov     eax, edi
0x14002ab1f  lea     r8, [rsp+270h+var_238]
0x14002ab24  add     r8, rax
0x14002ab27  lea     rcx, [rsp+270h+var_250]
0x14002ab2c  mov     edx, edi
0x14002ab2e  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x14002ab33  inc     edi
0x14002ab35  cmp     edi, 8
0x14002ab38  jb      short loc_14002AB1D
0x14002ab3a  mov     rcx, [rsi]
0x14002ab3d  lea     rdx, [rsp+270h+var_250]
0x14002ab42  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x14002ab47  mov     edi, eax
0x14002ab49  test    eax, eax
0x14002ab4b  js      loc_14002ACB3
0x14002ab51  lea     r8, [rsp+270h+nSize]; nSize
0x14002ab56  mov     [rsp+270h+nSize], 104h
0x14002ab5e  lea     rdx, [rsp+270h+NameBuffer]; lpNameBuffer
0x14002ab63  mov     ecx, 2; NameFormat
0x14002ab68  call    cs:__imp_GetUserNameExW
0x14002ab6e  test    al, al
0x14002ab70  jnz     short loc_14002AB90
0x14002ab72  call    cs:__imp_GetLastError
0x14002ab78  mov     edi, eax
0x14002ab7a  test    eax, eax
0x14002ab7c  jle     loc_14002ACB3
0x14002ab82  movzx   edi, ax
0x14002ab85  or      edi, 80070000h
0x14002ab8b  jmp     loc_14002ACB3
0x14002ab90  mov     rcx, [rsi]
0x14002ab93  lea     r8, [rsp+270h+rgsabound]
0x14002ab98  mov     edx, 9
0x14002ab9d  mov     qword ptr [rsp+270h+rgsabound.cElements], 0
0x14002aba6  mov     rax, [rcx]
0x14002aba9  mov     rax, [rax+50h]
0x14002abad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002abb2  mov     rcx, qword ptr [rsp+270h+rgsabound.cElements]
0x14002abb7  mov     edi, eax
0x14002abb9  test    eax, eax
0x14002abbb  js      loc_14002AC6A
0x14002abc1  mov     [rsp+270h+var_250], 0
0x14002abca  lea     r8, [rsp+270h+var_250]
0x14002abcf  mov     rax, [rcx]
0x14002abd2  lea     rdx, IID_ILogonTrigger
0x14002abd9  mov     rax, [rax]
0x14002abdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002abe1  mov     edi, eax
0x14002abe3  test    eax, eax
0x14002abe5  jns     short loc_14002ABEE
0x14002abe7  mov     rcx, [rsp+270h+var_250]
0x14002abec  jmp     short loc_14002AC54
0x14002abee  mov     rdi, [rsp+270h+var_250]
0x14002abf3  lea     rdx, [rsp+270h+NameBuffer]; unsigned __int16 *
0x14002abf8  lea     rcx, [rsp+270h+var_238]; this
0x14002abfd  mov     rax, [rdi]
0x14002ac00  mov     r14, [rax+0B8h]
0x14002ac07  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14002ac0c  mov     rdx, [rax]
0x14002ac0f  test    rdx, rdx
0x14002ac12  jz      short loc_14002AC17
0x14002ac14  mov     rdx, [rdx]
0x14002ac17  mov     rcx, rdi
0x14002ac1a  mov     rax, r14
0x14002ac1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac22  lea     rcx, [rsp+270h+var_238]; this
0x14002ac27  mov     edi, eax
0x14002ac29  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14002ac2e  mov     rcx, [rsp+270h+var_250]
0x14002ac33  test    edi, edi
0x14002ac35  js      short loc_14002AC54
0x14002ac37  mov     rax, [rcx]
0x14002ac3a  or      edx, 0FFFFFFFFh
0x14002ac3d  mov     rax, [rax+98h]
0x14002ac44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac49  mov     rcx, [rsp+270h+var_250]
0x14002ac4e  mov     edi, eax
0x14002ac50  test    eax, eax
0x14002ac52  jns     short loc_14002AC7D
0x14002ac54  test    rcx, rcx
0x14002ac57  jz      short loc_14002AC65
0x14002ac59  mov     rax, [rcx]
0x14002ac5c  mov     rax, [rax+10h]
0x14002ac60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac65  mov     rcx, qword ptr [rsp+270h+rgsabound.cElements]
0x14002ac6a  test    rcx, rcx
0x14002ac6d  jz      short loc_14002ACB3
0x14002ac6f  mov     rax, [rcx]
0x14002ac72  mov     rax, [rax+10h]
0x14002ac76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac7b  jmp     short loc_14002ACB3
0x14002ac7d  test    rcx, rcx
0x14002ac80  jz      short loc_14002AC8E
0x14002ac82  mov     rax, [rcx]
0x14002ac85  mov     rax, [rax+10h]
0x14002ac89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac8e  mov     rcx, qword ptr [rsp+270h+rgsabound.cElements]
0x14002ac93  test    rcx, rcx
0x14002ac96  jz      short loc_14002ACA4
0x14002ac98  mov     rax, [rcx]
0x14002ac9b  mov     rax, [rax+10h]
0x14002ac9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aca4  mov     rcx, [rsi]; struct ITriggerCollection *
0x14002aca7  lea     rdx, [rsp+270h+NameBuffer]; unsigned __int16 *
0x14002acac  call    ?AddTaskUnlockTrigger@@YAJPEAUITriggerCollection@@PEAG@Z; AddTaskUnlockTrigger(ITriggerCollection *,ushort *)
0x14002acb1  mov     edi, eax
0x14002acb3  test    rbx, rbx
0x14002acb6  jz      short loc_14002ACCE
0x14002acb8  mov     rcx, rbx; psa
0x14002acbb  call    cs:__imp_SafeArrayUnlock
0x14002acc1  test    eax, eax
0x14002acc3  js      short loc_14002ACCE
0x14002acc5  mov     rcx, rbx; psa
0x14002acc8  call    cs:__imp_SafeArrayDestroy
0x14002acce  mov     eax, edi
0x14002acd0  mov     rcx, [rbp+170h+var_20]
0x14002acd7  xor     rcx, rsp; StackCookie
0x14002acda  call    __security_check_cookie
0x14002acdf  lea     r11, [rsp+270h+var_10]
0x14002ace7  mov     rbx, [r11+28h]
0x14002aceb  mov     rsi, [r11+30h]
0x14002acef  mov     rsp, r11
0x14002acf2  pop     r14
0x14002acf4  pop     rdi
0x14002acf5  pop     rbp
0x14002acf6  retn
0x14002acf7  mov     eax, 8007000Eh
0x14002acfc  mov     ecx, eax; int
0x14002acfe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
