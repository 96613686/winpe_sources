# wil::details::functor_wrapper_void__lambda_8b2eda5c4de3e195837b02a7d86700e7___::Run

- ea: `0x18002e2c0`
- end: `0x18002e43b`
- name: `wil::details::functor_wrapper_void__lambda_8b2eda5c4de3e195837b02a7d86700e7___::Run`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002c19c`

## callees

- `0x1800034a0`
- `0x180010cac`
- `0x1800110fc`
- `0x180011194`
- `0x18002e2c0`
- `0x18002f2a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002e2d8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002e2d8`
- `deviceassociation!DafStartEnumCeremonies` at `0x18002e2f9`
- `deviceassociation!DafStartEnumCeremonies` at `0x18002e2f9`

## string_xrefs

- `0x18002e3a2`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002e426`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_8b2eda5c4de3e195837b02a7d86700e7___::Run(__int64 a1)
{
  unsigned int **v1; // rdi
  int v2; // r8d
  unsigned int *v3; // rbx
  int v4; // edx
  int v5; // r8d
  bool v7; // dl
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-38h]
  int v11; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = *(unsigned int ***)(a1 + 8);
  ResetEvent(*((HANDLE *)*v1 + 256));
  *v1[1] = DafStartEnumCeremonies(
             *((_QWORD *)*v1 + 255),
             0,
             0,
             Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_EnumCeremoniesCompleteCallback,
             *v1);
  if ( (*v1[1] & 0x80000000) != 0 )
  {
    v7 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v2, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v8 = wil::verify_hresult<long>(*v1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A1,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v8,
      v10);
  }
  v3 = v1[1];
  *v3 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)*v1);
  if ( (*v1[1] & 0x80000000) != 0 )
  {
    LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        v5,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v10,
        v11,
        73,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v9 = wil::verify_hresult<long>(*v1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A8,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v9,
      v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18002e2c0  mov     [rsp+arg_0], rbx
0x18002e2c5  push    rdi
0x18002e2c6  sub     rsp, 50h
0x18002e2ca  mov     rdi, [rcx+8]
0x18002e2ce  mov     rcx, [rdi]
0x18002e2d1  mov     rcx, [rcx+800h]; hEvent
0x18002e2d8  call    cs:__imp_ResetEvent
0x18002e2de  mov     rcx, [rdi]
0x18002e2e1  lea     r9, ?s_EnumCeremoniesCompleteCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXKPEBU_CEREMONY@@PEAXJ@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_EnumCeremoniesCompleteCallback(ulong,_CEREMONY const *,void *,long)
0x18002e2e8  mov     qword ptr [rsp+58h+var_38], rcx; int
0x18002e2ed  xor     r8d, r8d
0x18002e2f0  xor     edx, edx
0x18002e2f2  mov     rcx, [rcx+7F8h]
0x18002e2f9  call    cs:__imp_DafStartEnumCeremonies
0x18002e2ff  mov     rcx, [rdi+8]
0x18002e303  mov     [rcx], eax
0x18002e305  mov     rax, [rdi+8]
0x18002e309  cmp     dword ptr [rax], 0
0x18002e30c  jl      short loc_18002E338
0x18002e30e  mov     rcx, [rdi]; this
0x18002e311  mov     rbx, rax
0x18002e314  call    ?WaitForDafQueryEvent@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(void)
0x18002e319  mov     [rbx], eax
0x18002e31b  mov     rax, [rdi+8]
0x18002e31f  mov     r9d, [rax]
0x18002e322  test    r9d, r9d
0x18002e325  js      loc_18002E3B7
0x18002e32b  mov     rbx, [rsp+58h+arg_0]
0x18002e330  xor     eax, eax
0x18002e332  add     rsp, 50h
0x18002e336  pop     rdi
0x18002e337  retn
0x18002e338  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e33f  lea     rax, WPP_GLOBAL_Control
0x18002e346  cmp     rcx, rax
0x18002e349  jz      short loc_18002E355
0x18002e34b  cmp     byte ptr [rcx+19h], 2
0x18002e34f  jb      short loc_18002E355
0x18002e351  mov     dl, 1
0x18002e353  jmp     short loc_18002E357
0x18002e355  xor     dl, dl
0x18002e357  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e35e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e365  setnz   r8b
0x18002e369  test    dl, dl
0x18002e36b  jnz     short loc_18002E372
0x18002e36d  test    r8b, r8b
0x18002e370  jz      short loc_18002E392
0x18002e372  mov     r9, [rcx+28h]
0x18002e376  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e37d  mov     rcx, [rcx+10h]
0x18002e381  mov     [rsp+58h+var_20], rax
0x18002e386  mov     [rsp+58h+var_28], 48h ; 'H'
0x18002e38d  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002e392  mov     rcx, [rdi+8]
0x18002e396  mov     ecx, [rcx]
0x18002e398  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e39d  mov     rcx, [rsp+58h]; this
0x18002e3a2  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e3a9  mov     r9d, eax; char *
0x18002e3ac  mov     edx, 2A1h; void *
0x18002e3b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3be  lea     rax, WPP_GLOBAL_Control
0x18002e3c5  cmp     rcx, rax
0x18002e3c8  jz      short loc_18002E3D4
0x18002e3ca  cmp     byte ptr [rcx+19h], 2
0x18002e3ce  jb      short loc_18002E3D4
0x18002e3d0  mov     dl, 1
0x18002e3d2  jmp     short loc_18002E3D6
0x18002e3d4  xor     dl, dl
0x18002e3d6  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e3dd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e3e4  setnz   r8b
0x18002e3e8  test    dl, dl
0x18002e3ea  jnz     short loc_18002E3F1
0x18002e3ec  test    r8b, r8b
0x18002e3ef  jz      short loc_18002E416
0x18002e3f1  mov     [rsp+58h+var_10], r9d
0x18002e3f6  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e3fd  mov     r9, [rcx+28h]
0x18002e401  mov     rcx, [rcx+10h]
0x18002e405  mov     [rsp+58h+var_20], rax
0x18002e40a  mov     [rsp+58h+var_28], 49h ; 'I'
0x18002e411  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002e416  mov     rcx, [rdi+8]
0x18002e41a  mov     ecx, [rcx]
0x18002e41c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e421  mov     rcx, [rsp+58h]; this
0x18002e426  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e42d  mov     r9d, eax; char *
0x18002e430  mov     edx, 2A8h; void *
0x18002e435  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
