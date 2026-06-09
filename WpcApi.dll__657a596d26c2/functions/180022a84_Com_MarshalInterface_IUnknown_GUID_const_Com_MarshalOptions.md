# Com::MarshalInterface(IUnknown *,_GUID const &,Com::MarshalOptions)

- ea: `0x180022a84`
- end: `0x180022c40`
- name: `?MarshalInterface@Com@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIUnknown@@AEBU_GUID@@W4MarshalOptions@1@@Z`
- size: `444`
- prototype: `_QWORD *__fastcall(_QWORD *, IUnknown *, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b5c0`

## callees

- `0x180003d20`
- `0x1800195c4`
- `0x180022714`
- `0x180022a84`
- `0x1800230b8`
- `0x18002c010`

## import_xrefs

- `ole32!CoMarshalInterface` at `0x180022bcd`
- `ole32!CoMarshalInterface` at `0x180022bcd`

## pseudocode

```c
_QWORD *__fastcall Com::MarshalInterface(_QWORD *a1, IUnknown *a2, __int64 a3, int a4)
{
  __int64 v7; // rax
  DWORD v8; // r9d
  HRESULT v9; // ebx
  _QWORD v11[3]; // [rsp+50h] [rbp-31h] BYREF
  int v12; // [rsp+68h] [rbp-19h]
  _QWORD *v13; // [rsp+70h] [rbp-11h]
  void **v14; // [rsp+78h] [rbp-9h]
  void **v15; // [rsp+80h] [rbp-1h]
  _QWORD v16[3]; // [rsp+88h] [rbp+7h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+A0h] [rbp+1Fh] BYREF

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v14 = &RawMemoryStream::`vftable'{for `InputStream'};
  v15 = &RawMemoryStream::`vftable'{for `SeekableStream'};
  v16[0] = &RawMemoryStream::`vftable';
  v16[1] = a1;
  v16[2] = 0;
  v7 = qword_18004A6F0;
  if ( qword_18004A6F0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(qword_18004A6F0 + 8));
    v7 = qword_18004A6F0;
  }
  v11[0] = &Com::Object<IStream,Com::Private::NullType>::`vftable';
  v11[1] = Com::Module::FakeModule;
  v11[2] = v7;
  v12 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)Com::Module::FakeModule + 16LL))(Com::Module::FakeModule);
  v11[0] = &OutputStreamComAdapter::`vftable';
  v13 = v16;
  v8 = 3;
  if ( a4 != 1 )
    v8 = 0;
  v9 = CoMarshalInterface((LPSTREAM)v11, &GUID_b2adc88a_a140_4298_9d43_592e719a347a, a2, v8, 0, 0);
  if ( v9 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF__guid_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL));
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v9);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Com::Object<IStream,Com::Private::NullType>::~Object<IStream,Com::Private::NullType>((__int64)v11);
  return a1;
}

```

## disassembly

```asm
0x180022a84  mov     rax, rsp
0x180022a87  mov     [rax+10h], rbx
0x180022a8b  mov     [rax+20h], rsi
0x180022a8f  mov     [rax+18h], r8
0x180022a93  mov     [rax+8], rcx
0x180022a97  push    rbp
0x180022a98  push    rdi
0x180022a99  push    r14
0x180022a9b  lea     rbp, [rax-5Fh]
0x180022a9f  sub     rsp, 0C0h
0x180022aa6  mov     esi, r9d
0x180022aa9  mov     r14, rdx
0x180022aac  mov     rdi, rcx
0x180022aaf  mov     [rbp+57h+var_A0], 0
0x180022ab6  mov     qword ptr [rcx], 0
0x180022abd  mov     qword ptr [rcx+8], 0
0x180022ac5  mov     qword ptr [rcx+10h], 0
0x180022acd  mov     [rbp+57h+var_A0], 1
0x180022ad4  lea     rax, ??_7RawMemoryStream@@6BInputStream@@@; const RawMemoryStream::`vftable'{for `InputStream'}
0x180022adb  mov     [rbp+57h+var_60], rax
0x180022adf  lea     rax, ??_7RawMemoryStream@@6BSeekableStream@@@; const RawMemoryStream::`vftable'{for `SeekableStream'}
0x180022ae6  mov     [rbp+57h+var_58], rax
0x180022aea  lea     rax, ??_7RawMemoryStream@@6B@; const RawMemoryStream::`vftable'
0x180022af1  mov     [rbp+57h+var_50], rax
0x180022af5  mov     [rbp+57h+var_48], rcx
0x180022af9  mov     [rbp+57h+var_40], 0
0x180022b01  mov     rax, cs:qword_18004A6F0
0x180022b08  test    rax, rax
0x180022b0b  jz      short loc_180022B18
0x180022b0d  lock inc dword ptr [rax+8]
0x180022b11  mov     rax, cs:qword_18004A6F0
0x180022b18  lea     rcx, [rbp+57h+var_98]
0x180022b1c  mov     [rbp+57h+arg_10], rcx
0x180022b20  lea     rcx, ??_7?$Object@UIStream@@UNullType@Private@Com@@@Com@@6B@; const Com::Object<IStream,Com::Private::NullType>::`vftable'
0x180022b27  mov     [rbp+57h+var_88], rcx
0x180022b2b  mov     rcx, cs:?FakeModule@Module@Com@@2V?$shared_ref@VModule@Com@@@stdext@@B; stdext::shared_ref<Com::Module> const Com::Module::FakeModule
0x180022b32  mov     [rbp+57h+var_80], rcx
0x180022b36  mov     [rbp+57h+var_78], rax
0x180022b3a  xorps   xmm0, xmm0
0x180022b3d  movdqu  [rbp+57h+var_98], xmm0
0x180022b42  mov     [rbp+57h+var_70], 0
0x180022b49  mov     rax, [rcx]
0x180022b4c  mov     rax, [rax+10h]
0x180022b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b55  nop
0x180022b56  mov     rbx, qword ptr [rbp+57h+var_98+8]
0x180022b5a  test    rbx, rbx
0x180022b5d  jz      short loc_180022B96
0x180022b5f  or      eax, 0FFFFFFFFh
0x180022b62  lock xadd [rbx+8], eax
0x180022b67  cmp     eax, 1
0x180022b6a  jnz     short loc_180022B96
0x180022b6c  mov     rax, [rbx]
0x180022b6f  mov     rcx, rbx
0x180022b72  mov     rax, [rax]
0x180022b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b7a  or      eax, 0FFFFFFFFh
0x180022b7d  lock xadd [rbx+0Ch], eax
0x180022b82  cmp     eax, 1
0x180022b85  jnz     short loc_180022B96
0x180022b87  mov     rax, [rbx]
0x180022b8a  mov     rcx, rbx
0x180022b8d  mov     rax, [rax+8]
0x180022b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b96  lea     rax, ??_7OutputStreamComAdapter@@6B@; const OutputStreamComAdapter::`vftable'
0x180022b9d  mov     [rbp+57h+var_88], rax
0x180022ba1  lea     rax, [rbp+57h+var_50]
0x180022ba5  mov     [rbp+57h+var_68], rax
0x180022ba9  xor     eax, eax
0x180022bab  lea     r9d, [rax+3]
0x180022baf  cmp     esi, 1
0x180022bb2  cmovnz  r9d, eax; dwDestContext
0x180022bb6  mov     [rsp+0D0h+mshlflags], eax; mshlflags
0x180022bba  mov     [rsp+0D0h+pvDestContext], rax; pvDestContext
0x180022bbf  mov     r8, r14; pUnk
0x180022bc2  lea     rdx, _GUID_b2adc88a_a140_4298_9d43_592e719a347a; riid
0x180022bc9  lea     rcx, [rbp+57h+var_88]; pStm
0x180022bcd  call    cs:__imp_CoMarshalInterface
0x180022bd3  mov     ebx, eax
0x180022bd5  test    eax, eax
0x180022bd7  js      short loc_180022BFE
0x180022bd9  lea     rcx, [rbp+57h+var_88]
0x180022bdd  call    ??1?$Object@UIStream@@UNullType@Private@Com@@@Com@@UEAA@XZ; Com::Object<IStream,Com::Private::NullType>::~Object<IStream,Com::Private::NullType>(void)
0x180022be2  nop
0x180022be3  mov     rax, rdi
0x180022be6  lea     r11, [rsp+0D0h+var_10]
0x180022bee  mov     rbx, [r11+28h]
0x180022bf2  mov     rsi, [r11+38h]
0x180022bf6  mov     rsp, r11
0x180022bf9  pop     r14
0x180022bfb  pop     rdi
0x180022bfc  pop     rbp
0x180022bfd  retn
0x180022bfe  lea     rax, WPP_GLOBAL_Control
0x180022c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c0c  cmp     rcx, rax
0x180022c0f  jz      short loc_180022C24
0x180022c11  test    byte ptr [rcx+1Ch], 1
0x180022c15  jz      short loc_180022C24
0x180022c17  mov     dword ptr [rsp+0D0h+pvDestContext], ebx
0x180022c1b  mov     rcx, [rcx+10h]
0x180022c1f  call    WPP_SF__guid_d
0x180022c24  mov     edx, ebx; int
0x180022c26  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180022c2a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180022c2f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180022c36  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180022c3a  call    _CxxThrowException_0
```
