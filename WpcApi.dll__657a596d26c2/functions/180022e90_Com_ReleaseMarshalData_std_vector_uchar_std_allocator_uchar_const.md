# Com::ReleaseMarshalData(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180022e90`
- end: `0x180022f80`
- name: `?ReleaseMarshalData@Com@@YAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `240`
- prototype: `HRESULT __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b9c8`

## callees

- `0x180003d20`
- `0x18000b29c`
- `0x1800195c4`
- `0x180022e90`
- `0x180023dd0`
- `0x18002c010`

## import_xrefs

- `ole32!CoReleaseMarshalData` at `0x180022ed3`
- `ole32!CoReleaseMarshalData` at `0x180022ed3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall Com::ReleaseMarshalData(__int64 *a1)
{
  __int64 v1; // rdx
  HRESULT result; // eax
  int v3; // ebx
  volatile signed __int32 *v4; // rbx
  _QWORD v5[4]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v6[12]; // [rsp+40h] [rbp-58h] BYREF
  int v7; // [rsp+4Ch] [rbp-4Ch]
  volatile signed __int32 *v8; // [rsp+58h] [rbp-40h]
  _BYTE pExceptionObject[48]; // [rsp+68h] [rbp-30h] BYREF

  v1 = *a1;
  v5[0] = &MemoryInputStream::`vftable';
  v5[1] = v1;
  v5[2] = a1[1] - v1;
  v5[3] = 0;
  InputStreamComAdapter::InputStreamComAdapter((InputStreamComAdapter *)v6, (struct InputStream *)v5);
  result = CoReleaseMarshalData((LPSTREAM)v6);
  v3 = result;
  if ( result < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        13,
        WPP_739414dcde763814ece68798e3b2d74d_Traceguids,
        (unsigned int)result);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v3);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v4 = v8;
  if ( v8 )
  {
    result = _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF);
    if ( result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      result = _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF);
      if ( result == 1 )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v7 = -1073741823;
  return result;
}

```

## disassembly

```asm
0x180022e90  mov     r11, rsp
0x180022e93  push    rbx
0x180022e94  sub     rsp, 90h
0x180022e9b  mov     rdx, [rcx]
0x180022e9e  lea     rax, ??_7MemoryInputStream@@6B@; const MemoryInputStream::`vftable'
0x180022ea5  mov     [r11-78h], rax
0x180022ea9  mov     [r11-70h], rdx
0x180022ead  mov     rax, [rcx+8]
0x180022eb1  sub     rax, rdx
0x180022eb4  mov     [r11-68h], rax
0x180022eb8  mov     qword ptr [r11-60h], 0
0x180022ec0  lea     rdx, [r11-78h]; struct InputStream *
0x180022ec4  lea     rcx, [r11-58h]; this
0x180022ec8  call    ??0InputStreamComAdapter@@QEAA@AEAVInputStream@@@Z; InputStreamComAdapter::InputStreamComAdapter(InputStream &)
0x180022ecd  nop
0x180022ece  lea     rcx, [rsp+98h+var_58]; pStm
0x180022ed3  call    cs:__imp_CoReleaseMarshalData
0x180022ed9  mov     ebx, eax
0x180022edb  test    eax, eax
0x180022edd  js      short loc_180022F31
0x180022edf  mov     rbx, [rsp+98h+var_40]
0x180022ee4  test    rbx, rbx
0x180022ee7  jz      short loc_180022F20
0x180022ee9  or      eax, 0FFFFFFFFh
0x180022eec  lock xadd [rbx+8], eax
0x180022ef1  cmp     eax, 1
0x180022ef4  jnz     short loc_180022F20
0x180022ef6  mov     rax, [rbx]
0x180022ef9  mov     rcx, rbx
0x180022efc  mov     rax, [rax]
0x180022eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f04  or      eax, 0FFFFFFFFh
0x180022f07  lock xadd [rbx+0Ch], eax
0x180022f0c  cmp     eax, 1
0x180022f0f  jnz     short loc_180022F20
0x180022f11  mov     rax, [rbx]
0x180022f14  mov     rcx, rbx
0x180022f17  mov     rax, [rax+8]
0x180022f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f20  mov     [rsp+98h+var_4C], 0C0000001h
0x180022f28  add     rsp, 90h
0x180022f2f  pop     rbx
0x180022f30  retn
0x180022f31  lea     rax, WPP_GLOBAL_Control
0x180022f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f3f  cmp     rcx, rax
0x180022f42  jz      short loc_180022F62
0x180022f44  test    byte ptr [rcx+1Ch], 1
0x180022f48  jz      short loc_180022F62
0x180022f4a  mov     edx, 0Dh
0x180022f4f  mov     r9d, ebx
0x180022f52  lea     r8, WPP_739414dcde763814ece68798e3b2d74d_Traceguids
0x180022f59  mov     rcx, [rcx+10h]
0x180022f5d  call    WPP_SF_d
0x180022f62  mov     edx, ebx; int
0x180022f64  lea     rcx, [rsp+98h+pExceptionObject]; this
0x180022f69  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180022f6e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180022f75  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180022f7a  call    _CxxThrowException_0
```
