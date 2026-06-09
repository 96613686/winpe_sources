# RegKey::DeleteValue(ushort const *)

- ea: `0x18000e440`
- end: `0x18000e54a`
- name: `?DeleteValue@RegKey@@QEBAXPEBG@Z`
- size: `266`
- prototype: `void __fastcall(RegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001020c`

## callees

- `0x1800012e0`
- `0x1800012f0`
- `0x18000211c`
- `0x1800021e4`
- `0x18000e010`
- `0x18000e440`
- `0x18000f0bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e45d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000e45d`

## pseudocode

```c
void __fastcall RegKey::DeleteValue(RegKey *this, const unsigned __int16 *a2)
{
  _QWORD *v2; // rdi
  HKEY v4; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // r8d
  _QWORD *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v16; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+70h] [rbp+18h]
  const unsigned __int16 *v18; // [rsp+78h] [rbp+20h] BYREF

  v2 = (_QWORD *)((char *)this + 8);
  v4 = (HKEY)*((_QWORD *)this + 1);
  if ( !v4 )
    v4 = *(HKEY *)this;
  v6 = RegDeleteValueW(v4, a2);
  if ( (v6 & 0xFFFFFFFD) != 0 )
  {
    v10 = dword_18001C010;
    if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 2) )
    {
      v17 = v6;
      v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator bool(v2);
      v11 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v18, (__int64)a2);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        (__int64)&v16,
        (__int64)&byte_18001760F,
        v12,
        v13,
        v11);
    }
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x1FE, v10, (const char *)v6, v14);
  }
  if ( (unsigned int)dword_18001C010 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_18001C010, 2) )
    {
      v18 = a2;
      v16 = v6 == 0;
      LOBYTE(v17) = *v2 != 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v7,
        (__int64)qword_180017568,
        v8,
        v9,
        &v18);
    }
  }
}

```

## disassembly

```asm
0x18000e440  push    rbx
0x18000e442  push    rsi
0x18000e443  push    rdi
0x18000e444  sub     rsp, 40h
0x18000e448  lea     rdi, [rcx+8]
0x18000e44c  mov     rax, rcx
0x18000e44f  mov     rcx, [rdi]
0x18000e452  mov     rsi, rdx
0x18000e455  test    rcx, rcx
0x18000e458  jnz     short loc_18000E45D
0x18000e45a  mov     rcx, [rax]; hKey
0x18000e45d  call    cs:__imp_RegDeleteValueW
0x18000e463  mov     ebx, eax
0x18000e465  test    eax, 0FFFFFFFDh
0x18000e46a  jnz     short loc_18000E4D3
0x18000e46c  mov     eax, cs:dword_18001C010
0x18000e472  cmp     eax, 4
0x18000e475  jbe     short loc_18000E4CB
0x18000e477  mov     edx, 2
0x18000e47c  lea     rcx, dword_18001C010
0x18000e483  call    _tlgKeywordOn
0x18000e488  test    al, al
0x18000e48a  jz      short loc_18000E4CB
0x18000e48c  test    ebx, ebx
0x18000e48e  mov     [rsp+58h+arg_18], rsi
0x18000e493  lea     rax, [rsp+58h+arg_0]
0x18000e498  mov     [rsp+58h+var_28], rax
0x18000e49d  lea     rdx, qword_180017568
0x18000e4a4  lea     rax, [rsp+58h+arg_10]
0x18000e4a9  setz    [rsp+58h+arg_0]
0x18000e4ae  cmp     qword ptr [rdi], 0
0x18000e4b2  mov     [rsp+58h+var_30], rax
0x18000e4b7  lea     rax, [rsp+58h+arg_18]
0x18000e4bc  mov     qword ptr [rsp+58h+var_38], rax
0x18000e4c1  setnz   byte ptr [rsp+58h+arg_10]
0x18000e4c6  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18000e4cb  add     rsp, 40h
0x18000e4cf  pop     rdi
0x18000e4d0  pop     rsi
0x18000e4d1  pop     rbx
0x18000e4d2  retn
0x18000e4d3  mov     r8d, cs:dword_18001C010
0x18000e4da  cmp     r8d, 2
0x18000e4de  jbe     short loc_18000E537
0x18000e4e0  mov     edx, 2
0x18000e4e5  lea     rcx, dword_18001C010
0x18000e4ec  call    _tlgKeywordOn
0x18000e4f1  test    al, al
0x18000e4f3  jz      short loc_18000E537
0x18000e4f5  mov     rcx, rdi
0x18000e4f8  mov     [rsp+58h+arg_10], ebx
0x18000e4fc  call    ??B?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBA_NXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator bool(void)
0x18000e501  mov     rdx, rsi
0x18000e504  mov     [rsp+58h+arg_0], al
0x18000e508  lea     rcx, [rsp+58h+arg_18]
0x18000e50d  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000e512  lea     rcx, [rsp+58h+arg_10]
0x18000e517  mov     [rsp+58h+var_28], rcx
0x18000e51c  lea     rdx, byte_18001760F
0x18000e523  lea     rcx, [rsp+58h+arg_0]
0x18000e528  mov     [rsp+58h+var_30], rcx
0x18000e52d  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18000e532  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18000e537  mov     rcx, [rsp+58h]; this
0x18000e53c  mov     r9d, ebx; char *
0x18000e53f  mov     edx, 1FEh; void *
0x18000e544  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
