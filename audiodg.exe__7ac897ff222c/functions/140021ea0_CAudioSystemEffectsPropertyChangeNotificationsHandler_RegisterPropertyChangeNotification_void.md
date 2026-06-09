# CAudioSystemEffectsPropertyChangeNotificationsHandler::RegisterPropertyChangeNotification(void)

- ea: `0x140021ea0`
- end: `0x140022020`
- name: `?RegisterPropertyChangeNotification@CAudioSystemEffectsPropertyChangeNotificationsHandler@@AEAAJXZ`
- size: `384`
- prototype: `__int64 __fastcall(CAudioSystemEffectsPropertyChangeNotificationsHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140021df4`

## callees

- `0x14000c33c`
- `0x140021ea0`
- `0x140022028`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140021f9b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140021fc5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140021f9b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140021fc5`
- `PROPSYS!InitPropVariantFromCLSID` at `0x140021eda`
- `PROPSYS!InitPropVariantFromCLSID` at `0x140021eda`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAudioSystemEffectsPropertyChangeNotificationsHandler::RegisterPropertyChangeNotification(
        CAudioSystemEffectsPropertyChangeNotificationsHandler *this)
{
  HRESULT inited; // eax
  unsigned int v4; // edi
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, GUID *, __int64, PROPVARIANT *); // rsi
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // esi
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-58h]
  PROPVARIANT ppropvar[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  CAudioSystemEffectsPropertyChangeNotificationsHandler *v16; // [rsp+80h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 136) )
    return 0;
  *(_OWORD *)ppropvar = 0;
  v14 = 0;
  inited = InitPropVariantFromCLSID((const IID *const)((char *)this + 40), ppropvar);
  v4 = inited;
  if ( inited < 0 )
  {
    v11 = 47;
  }
  else
  {
    v5 = *((_QWORD *)this + 11);
    v6 = *(__int64 (__fastcall **)(__int64, GUID *, __int64, PROPVARIANT *))(*(_QWORD *)v5 + 24LL);
    v7 = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v12 = (_DWORD)this + 144;
    inited = v6(v5, &GUID_302ae7f9_d7e0_43e4_971b_1f8293613d2a, 1, ppropvar);
    v4 = inited;
    if ( inited < 0 )
    {
      v11 = 49;
    }
    else
    {
      v16 = this;
      v8 = *((_QWORD *)this + 23);
      *((_QWORD *)this + 23) = 0;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v9 = Microsoft::WRL::Details::MakeAndInitialize<CAudioSystemEffectsPropertyChangeNotificationsDelegator,CAudioSystemEffectsPropertyChangeNotificationsDelegator,CAudioSystemEffectsPropertyChangeNotificationsHandler *>(
             (char *)this + 184,
             &v16);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectspropertychangenotificationshandler.cpp",
          (const char *)(unsigned int)v9,
          v12);
        v4 = v10;
        goto LABEL_14;
      }
      inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 18) + 64LL))(
                 *((_QWORD *)this + 18),
                 *((_QWORD *)this + 23));
      v4 = inited;
      if ( inited >= 0 )
      {
        *((_BYTE *)this + 136) = 1;
        PropVariantClear(ppropvar);
        return 0;
      }
      v11 = 51;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiosystemeffectspropertychangenotificationshandler.cpp",
    (const char *)(unsigned int)inited,
    v12);
LABEL_14:
  PropVariantClear(ppropvar);
  return v4;
}

```

## disassembly

```asm
0x140021ea0  push    rbx
0x140021ea2  push    rsi
0x140021ea3  push    rdi
0x140021ea4  push    r14
0x140021ea6  sub     rsp, 58h
0x140021eaa  mov     rbx, rcx
0x140021ead  cmp     byte ptr [rcx+88h], 0
0x140021eb4  jz      short loc_140021EC2
0x140021eb6  xor     eax, eax
0x140021eb8  add     rsp, 58h
0x140021ebc  pop     r14
0x140021ebe  pop     rdi
0x140021ebf  pop     rsi
0x140021ec0  pop     rbx
0x140021ec1  retn
0x140021ec2  xorps   xmm0, xmm0
0x140021ec5  xor     eax, eax
0x140021ec7  movups  xmmword ptr [rsp+78h+ppropvar], xmm0
0x140021ecc  mov     [rsp+78h+var_38], rax
0x140021ed1  add     rcx, 28h ; '('; clsid
0x140021ed5  lea     rdx, [rsp+78h+ppropvar]; ppropvar
0x140021eda  call    cs:__imp_InitPropVariantFromCLSID
0x140021ee0  mov     edi, eax
0x140021ee2  test    eax, eax
0x140021ee4  js      loc_140021FD2
0x140021eea  mov     rdi, [rbx+58h]
0x140021eee  mov     rax, [rdi]
0x140021ef1  mov     rsi, [rax+18h]
0x140021ef5  lea     r14, [rbx+90h]
0x140021efc  mov     rcx, [r14]
0x140021eff  mov     qword ptr [r14], 0
0x140021f06  test    rcx, rcx
0x140021f09  jnz     loc_140021FD9
0x140021f0f  mov     qword ptr [rsp+78h+var_58], r14; int
0x140021f14  lea     r9, [rsp+78h+ppropvar]
0x140021f19  mov     r8d, 1
0x140021f1f  lea     rdx, _GUID_302ae7f9_d7e0_43e4_971b_1f8293613d2a
0x140021f26  mov     rcx, rdi
0x140021f29  mov     rax, rsi
0x140021f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021f31  mov     edi, eax
0x140021f33  test    eax, eax
0x140021f35  js      short loc_140021FA6
0x140021f37  mov     [rsp+78h+arg_0], rbx
0x140021f3f  lea     rdi, [rbx+0B8h]
0x140021f46  mov     rcx, [rdi]
0x140021f49  mov     qword ptr [rdi], 0
0x140021f50  test    rcx, rcx
0x140021f53  jnz     loc_140021FEA
0x140021f59  lea     rdx, [rsp+78h+arg_0]
0x140021f61  mov     rcx, rdi
0x140021f64  call    ??$MakeAndInitialize@VCAudioSystemEffectsPropertyChangeNotificationsDelegator@@V1@PEAVCAudioSystemEffectsPropertyChangeNotificationsHandler@@@Details@WRL@Microsoft@@YAJPEAPEAVCAudioSystemEffectsPropertyChangeNotificationsDelegator@@$$QEAPEAVCAudioSystemEffectsPropertyChangeNotificationsHandler@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioSystemEffectsPropertyChangeNotificationsDelegator,CAudioSystemEffectsPropertyChangeNotificationsDelegator,CAudioSystemEffectsPropertyChangeNotificationsHandler *>(CAudioSystemEffectsPropertyChangeNotificationsDelegator * *,CAudioSystemEffectsPropertyChangeNotificationsHandler * &&)
0x140021f69  mov     esi, eax
0x140021f6b  test    eax, eax
0x140021f6d  js      loc_140021FFB
0x140021f73  mov     rcx, [r14]
0x140021f76  mov     rax, [rcx]
0x140021f79  mov     rdx, [rdi]
0x140021f7c  mov     rax, [rax+40h]
0x140021f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021f85  mov     edi, eax
0x140021f87  test    eax, eax
0x140021f89  js      loc_140022018
0x140021f8f  mov     byte ptr [rbx+88h], 1
0x140021f96  lea     rcx, [rsp+78h+ppropvar]; pvar
0x140021f9b  call    cs:__imp_PropVariantClear
0x140021fa1  jmp     loc_140021EB6
0x140021fa6  mov     edx, 31h ; '1'; void *
0x140021fab  mov     r9d, eax; char *
0x140021fae  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140021fb5  mov     rcx, [rsp+78h]; this
0x140021fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021fbf  nop
0x140021fc0  lea     rcx, [rsp+78h+ppropvar]; pvar
0x140021fc5  call    cs:__imp_PropVariantClear
0x140021fcb  mov     eax, edi
0x140021fcd  jmp     loc_140021EB8
0x140021fd2  mov     edx, 2Fh ; '/'
0x140021fd7  jmp     short loc_140021FAB
0x140021fd9  mov     rax, [rcx]
0x140021fdc  mov     rax, [rax+10h]
0x140021fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021fe5  jmp     loc_140021F0F
0x140021fea  mov     rax, [rcx]
0x140021fed  mov     rax, [rax+10h]
0x140021ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021ff6  jmp     loc_140021F59
0x140021ffb  mov     rcx, [rsp+78h]; this
0x140022000  mov     r9d, esi; char *
0x140022003  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14002200a  mov     edx, 32h ; '2'; void *
0x14002200f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022014  mov     edi, esi
0x140022016  jmp     short loc_140021FC0
0x140022018  mov     edx, 33h ; '3'
0x14002201d  jmp     short loc_140021FAB
```
