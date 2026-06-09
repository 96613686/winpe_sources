# TaskSchedulerSignalFactory::AddWeeklyDay(__int64,Microsoft::WRL::ComPtr<ITaskFolder>,TimeSignal::Day const &,ushort const *,short,std::vector<_bstr_t,std::allocator<_bstr_t>> *)

- ea: `0x180029cf0`
- end: `0x180029fa0`
- name: `?AddWeeklyDay@TaskSchedulerSignalFactory@@AEAAJ_JV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBUDay@TimeSignal@@PEBGFPEAV?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(__int64, LONGLONG, __int64 *, _BYTE *, unsigned __int16 *, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a978`

## callees

- `0x180014e7c`
- `0x18001fb2c`
- `0x18002072c`
- `0x180028d88`
- `0x180028e74`
- `0x1800295b0`
- `0x180029a08`
- `0x180029cf0`
- `0x18002be88`
- `0x18002bfac`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180029da9`
- `OLEAUT32!__imp_VariantClear` at `0x180029ed7`
- `OLEAUT32!__imp_VariantClear` at `0x180029da9`
- `OLEAUT32!__imp_VariantClear` at `0x180029ed7`

## string_xrefs

- `0x180029e2c`: `RegisterTask( day.startTime, TimeSignal::Repeat::Weekly, dayBit, folder, startTaskName)`
- `0x180029f5a`: `RegisterTask( day.endTime, TimeSignal::Repeat::Weekly, dayBit, folder, endTaskName)`

## pseudocode

```c
__int64 __fastcall TaskSchedulerSignalFactory::AddWeeklyDay(
        __int64 a1,
        LONGLONG a2,
        __int64 *a3,
        _BYTE *a4,
        unsigned __int16 *a5,
        unsigned __int16 a6,
        __int64 a7)
{
  __int64 v11; // rdi
  _bstr_t *v12; // rbx
  _bstr_t *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 *v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 **v19; // rcx
  _bstr_t *v20; // rbx
  _bstr_t *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  __int64 *v27; // [rsp+30h] [rbp-40h] BYREF
  __int64 v28; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v29[8]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v30[8]; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v31[8]; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  __int64 *v33; // [rsp+B8h] [rbp+48h] BYREF

  v11 = a7;
  if ( !*a4 )
  {
LABEL_10:
    if ( a4[20] )
    {
      v20 = _bstr_t::_bstr_t((_bstr_t *)v31, L"Timer_End_");
      pvarg.vt = 20;
      pvarg.llVal = a2;
      v21 = _bstr_t::_bstr_t((_bstr_t *)v29, (const struct _variant_t *)&pvarg);
      v22 = _bstr_t::operator+(v20, v30, v21);
      _bstr_t::_bstr_t((_bstr_t *)&v28, a5);
      _bstr_t::operator+(v22, &v27, &v28);
      _bstr_t::_Free((_bstr_t *)&v28);
      _bstr_t::_Free((_bstr_t *)v30);
      _bstr_t::_Free((_bstr_t *)v29);
      VariantClear(&pvarg);
      _bstr_t::_Free((_bstr_t *)v31);
      v23 = *(_QWORD *)(v11 + 8);
      if ( v23 == *(_QWORD *)(v11 + 16) )
      {
        std::vector<_bstr_t>::_Emplace_reallocate<_bstr_t const &>(v11, *(_QWORD *)(v11 + 8), &v27);
      }
      else
      {
        std::_Construct_in_place<_bstr_t,_bstr_t const &>(v23, &v27);
        *(_QWORD *)(v11 + 8) += 8LL;
      }
      v24 = *a3;
      v28 = v24;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      v25 = TaskSchedulerSignalFactory::RegisterTask(a1, (__int64)(a4 + 24), 1, a6, &v28, &v27);
      v18 = v25;
      if ( v25 < 0 )
      {
        LogOpFailure(
          "RegisterTask( day.endTime, TimeSignal::Repeat::Weekly, dayBit, folder, endTaskName)",
          (unsigned int)v25);
        v19 = &v27;
        goto LABEL_18;
      }
      _bstr_t::_Free((_bstr_t *)&v27);
    }
    v18 = 0;
    goto LABEL_21;
  }
  v12 = _bstr_t::_bstr_t((_bstr_t *)v30, L"Timer_Begin_");
  pvarg.vt = 20;
  pvarg.llVal = a2;
  v13 = _bstr_t::_bstr_t((_bstr_t *)v29, (const struct _variant_t *)&pvarg);
  v14 = _bstr_t::operator+(v12, &v28, v13);
  _bstr_t::_bstr_t((_bstr_t *)&v27, a5);
  _bstr_t::operator+(v14, &v33, &v27);
  _bstr_t::_Free((_bstr_t *)&v27);
  _bstr_t::_Free((_bstr_t *)&v28);
  _bstr_t::_Free((_bstr_t *)v29);
  VariantClear(&pvarg);
  _bstr_t::_Free((_bstr_t *)v30);
  v15 = *(_QWORD *)(v11 + 8);
  if ( v15 == *(_QWORD *)(v11 + 16) )
  {
    std::vector<_bstr_t>::_Emplace_reallocate<_bstr_t const &>(v11, *(_QWORD *)(v11 + 8), &v33);
  }
  else
  {
    std::_Construct_in_place<_bstr_t,_bstr_t const &>(v15, &v33);
    *(_QWORD *)(v11 + 8) += 8LL;
  }
  v16 = (__int64 *)*a3;
  v27 = v16;
  if ( v16 )
    (*(void (__fastcall **)(__int64 *))(*v16 + 8))(v16);
  v17 = TaskSchedulerSignalFactory::RegisterTask(a1, (__int64)(a4 + 4), 1, a6, (__int64 *)&v27, &v33);
  v18 = v17;
  if ( v17 >= 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v33);
    goto LABEL_10;
  }
  LogOpFailure(
    "RegisterTask( day.startTime, TimeSignal::Repeat::Weekly, dayBit, folder, startTaskName)",
    (unsigned int)v17);
  v19 = &v33;
LABEL_18:
  _bstr_t::_Free((_bstr_t *)v19);
LABEL_21:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
  return v18;
}

```

## disassembly

```asm
0x180029cf0  mov     [rsp-28h+arg_0], rbx
0x180029cf5  mov     [rsp-28h+arg_8], rsi
0x180029cfa  mov     [rsp-28h+arg_10], r8
0x180029cff  push    rbp
0x180029d00  push    rdi
0x180029d01  push    r12
0x180029d03  push    r14
0x180029d05  push    r15
0x180029d07  mov     rbp, rsp
0x180029d0a  sub     rsp, 70h
0x180029d0e  mov     r14, r9
0x180029d11  mov     rsi, r8
0x180029d14  mov     r12, rdx
0x180029d17  mov     r15, rcx
0x180029d1a  mov     rdi, [rbp+arg_30]
0x180029d1e  cmp     byte ptr [r9], 0
0x180029d22  jz      loc_180029E4B
0x180029d28  lea     rdx, aTimerBegin; "Timer_Begin_"
0x180029d2f  lea     rcx, [rbp+var_28]; this
0x180029d33  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180029d38  mov     rbx, rax
0x180029d3b  mov     eax, 14h
0x180029d40  mov     word ptr [rbp+pvarg], ax
0x180029d44  mov     qword ptr [rbp+pvarg+8], r12
0x180029d48  lea     rdx, [rbp+pvarg]; struct _variant_t *
0x180029d4c  lea     rcx, [rbp+var_30]; this
0x180029d50  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180029d55  nop
0x180029d56  mov     r8, rax
0x180029d59  lea     rdx, [rbp+var_38]
0x180029d5d  mov     rcx, rbx
0x180029d60  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x180029d65  mov     rbx, rax
0x180029d68  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x180029d6c  lea     rcx, [rbp+var_40]; this
0x180029d70  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180029d75  nop
0x180029d76  lea     r8, [rbp+var_40]
0x180029d7a  lea     rdx, [rbp+arg_18]
0x180029d7e  mov     rcx, rbx
0x180029d81  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x180029d86  nop
0x180029d87  lea     rcx, [rbp+var_40]; this
0x180029d8b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029d90  nop
0x180029d91  lea     rcx, [rbp+var_38]; this
0x180029d95  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029d9a  nop
0x180029d9b  lea     rcx, [rbp+var_30]; this
0x180029d9f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029da4  nop
0x180029da5  lea     rcx, [rbp+pvarg]; pvarg
0x180029da9  call    cs:__imp_VariantClear
0x180029daf  nop
0x180029db0  lea     rcx, [rbp+var_28]; this
0x180029db4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029db9  mov     rcx, [rdi+8]
0x180029dbd  cmp     rcx, [rdi+10h]
0x180029dc1  jz      short loc_180029DD3
0x180029dc3  lea     rdx, [rbp+arg_18]
0x180029dc7  call    ??$_Construct_in_place@V_bstr_t@@AEBV1@@std@@YAXAEAV_bstr_t@@AEBV1@@Z; std::_Construct_in_place<_bstr_t,_bstr_t const &>(_bstr_t &,_bstr_t const &)
0x180029dcc  add     qword ptr [rdi+8], 8
0x180029dd1  jmp     short loc_180029DE2
0x180029dd3  lea     r8, [rbp+arg_18]
0x180029dd7  mov     rdx, rcx
0x180029dda  mov     rcx, rdi
0x180029ddd  call    ??$_Emplace_reallocate@AEBV_bstr_t@@@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAAPEAV_bstr_t@@QEAV2@AEBV2@@Z; std::vector<_bstr_t>::_Emplace_reallocate<_bstr_t const &>(_bstr_t * const,_bstr_t const &)
0x180029de2  mov     rcx, [rsi]
0x180029de5  mov     [rbp+var_40], rcx
0x180029de9  test    rcx, rcx
0x180029dec  jz      short loc_180029DFB
0x180029dee  mov     rax, [rcx]
0x180029df1  mov     rax, [rax+8]
0x180029df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dfa  nop
0x180029dfb  lea     rdx, [r14+4]
0x180029dff  lea     rax, [rbp+arg_18]
0x180029e03  mov     [rsp+70h+var_48], rax
0x180029e08  lea     rax, [rbp+var_40]
0x180029e0c  mov     [rsp+70h+var_50], rax
0x180029e11  movzx   r9d, [rbp+arg_28]
0x180029e16  mov     r8d, 1
0x180029e1c  mov     rcx, r15
0x180029e1f  call    ?RegisterTask@TaskSchedulerSignalFactory@@AEAAJAEBUTime@TimeSignal@@W4Repeat@3@FV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBV_bstr_t@@@Z; TaskSchedulerSignalFactory::RegisterTask(TimeSignal::Time const &,TimeSignal::Repeat,short,Microsoft::WRL::ComPtr<ITaskFolder>,_bstr_t const &)
0x180029e24  mov     ebx, eax
0x180029e26  test    eax, eax
0x180029e28  jns     short loc_180029E42
0x180029e2a  mov     edx, eax
0x180029e2c  lea     rcx, aRegistertaskDa; "RegisterTask( day.startTime, TimeSignal"...
0x180029e33  call    LogOpFailure
0x180029e38  nop
0x180029e39  lea     rcx, [rbp+arg_18]
0x180029e3d  jmp     loc_180029F6B
0x180029e42  lea     rcx, [rbp+arg_18]; this
0x180029e46  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029e4b  cmp     byte ptr [r14+14h], 0
0x180029e50  jz      loc_180029F7B
0x180029e56  lea     rdx, aTimerEnd; "Timer_End_"
0x180029e5d  lea     rcx, [rbp+var_20]; this
0x180029e61  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180029e66  mov     rbx, rax
0x180029e69  mov     eax, 14h
0x180029e6e  mov     word ptr [rbp+pvarg], ax
0x180029e72  mov     qword ptr [rbp+pvarg+8], r12
0x180029e76  lea     rdx, [rbp+pvarg]; struct _variant_t *
0x180029e7a  lea     rcx, [rbp+var_30]; this
0x180029e7e  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180029e83  nop
0x180029e84  mov     r8, rax
0x180029e87  lea     rdx, [rbp+var_28]
0x180029e8b  mov     rcx, rbx
0x180029e8e  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x180029e93  mov     rbx, rax
0x180029e96  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x180029e9a  lea     rcx, [rbp+var_38]; this
0x180029e9e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180029ea3  nop
0x180029ea4  lea     r8, [rbp+var_38]
0x180029ea8  lea     rdx, [rbp+var_40]
0x180029eac  mov     rcx, rbx
0x180029eaf  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x180029eb4  nop
0x180029eb5  lea     rcx, [rbp+var_38]; this
0x180029eb9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029ebe  nop
0x180029ebf  lea     rcx, [rbp+var_28]; this
0x180029ec3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029ec8  nop
0x180029ec9  lea     rcx, [rbp+var_30]; this
0x180029ecd  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029ed2  nop
0x180029ed3  lea     rcx, [rbp+pvarg]; pvarg
0x180029ed7  call    cs:__imp_VariantClear
0x180029edd  nop
0x180029ede  lea     rcx, [rbp+var_20]; this
0x180029ee2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029ee7  mov     rcx, [rdi+8]
0x180029eeb  cmp     rcx, [rdi+10h]
0x180029eef  jz      short loc_180029F01
0x180029ef1  lea     rdx, [rbp+var_40]
0x180029ef5  call    ??$_Construct_in_place@V_bstr_t@@AEBV1@@std@@YAXAEAV_bstr_t@@AEBV1@@Z; std::_Construct_in_place<_bstr_t,_bstr_t const &>(_bstr_t &,_bstr_t const &)
0x180029efa  add     qword ptr [rdi+8], 8
0x180029eff  jmp     short loc_180029F10
0x180029f01  lea     r8, [rbp+var_40]
0x180029f05  mov     rdx, rcx
0x180029f08  mov     rcx, rdi
0x180029f0b  call    ??$_Emplace_reallocate@AEBV_bstr_t@@@?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@AEAAPEAV_bstr_t@@QEAV2@AEBV2@@Z; std::vector<_bstr_t>::_Emplace_reallocate<_bstr_t const &>(_bstr_t * const,_bstr_t const &)
0x180029f10  mov     rcx, [rsi]
0x180029f13  mov     [rbp+var_38], rcx
0x180029f17  test    rcx, rcx
0x180029f1a  jz      short loc_180029F29
0x180029f1c  mov     rax, [rcx]
0x180029f1f  mov     rax, [rax+8]
0x180029f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f28  nop
0x180029f29  lea     rdx, [r14+18h]
0x180029f2d  lea     rax, [rbp+var_40]
0x180029f31  mov     [rsp+70h+var_48], rax
0x180029f36  lea     rax, [rbp+var_38]
0x180029f3a  mov     [rsp+70h+var_50], rax
0x180029f3f  movzx   r9d, [rbp+arg_28]
0x180029f44  mov     r8d, 1
0x180029f4a  mov     rcx, r15
0x180029f4d  call    ?RegisterTask@TaskSchedulerSignalFactory@@AEAAJAEBUTime@TimeSignal@@W4Repeat@3@FV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBV_bstr_t@@@Z; TaskSchedulerSignalFactory::RegisterTask(TimeSignal::Time const &,TimeSignal::Repeat,short,Microsoft::WRL::ComPtr<ITaskFolder>,_bstr_t const &)
0x180029f52  mov     ebx, eax
0x180029f54  test    eax, eax
0x180029f56  jns     short loc_180029F72
0x180029f58  mov     edx, eax
0x180029f5a  lea     rcx, aRegistertaskDa_0; "RegisterTask( day.endTime, TimeSignal::"...
0x180029f61  call    LogOpFailure
0x180029f66  nop
0x180029f67  lea     rcx, [rbp+var_40]; this
0x180029f6b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029f70  jmp     short loc_180029F7D
0x180029f72  lea     rcx, [rbp+var_40]; this
0x180029f76  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180029f7b  xor     ebx, ebx
0x180029f7d  mov     rcx, rsi
0x180029f80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029f85  mov     eax, ebx
0x180029f87  lea     r11, [rsp+70h+var_s0]
0x180029f8c  mov     rbx, [r11+30h]
0x180029f90  mov     rsi, [r11+38h]
0x180029f94  mov     rsp, r11
0x180029f97  pop     r15
0x180029f99  pop     r14
0x180029f9b  pop     r12
0x180029f9d  pop     rdi
0x180029f9e  pop     rbp
0x180029f9f  retn
```
