# RegKey::SetValue(ushort const *,ulong,void const *,unsigned __int64)

- ea: `0x18000efb8`
- end: `0x18000f0b4`
- name: `?SetValue@RegKey@@AEBAXPEBGKPEBX_K@Z`
- size: `252`
- prototype: `void __fastcall(RegKey *this, const unsigned __int16 *, unsigned int, const BYTE *, unsigned __int64 cbData)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000ee3c`
- `0x18000eef0`

## callees

- `0x1800012e0`
- `0x1800012f0`
- `0x1800022ac`
- `0x18000e010`
- `0x18000efb8`
- `0x18000f0bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000efff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000efff`

## pseudocode

```c
void __fastcall RegKey::SetValue(
        RegKey *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const BYTE *a4,
        unsigned __int64 cbData)
{
  char *v7; // rdi
  HKEY v8; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  _QWORD *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int lpData; // [rsp+20h] [rbp-58h]
  unsigned int lpDataa; // [rsp+20h] [rbp-58h]
  _QWORD v16[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( cbData > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x102, a3, (const char *)0x57, lpData);
  v7 = (char *)this + 8;
  v8 = (HKEY)*((_QWORD *)this + 1);
  if ( !v8 )
    v8 = *(HKEY *)this;
  v9 = RegSetValueExW(v8, a2, 0, a3, a4, cbData);
  if ( v9 )
  {
    v10 = dword_18001C010;
    if ( (unsigned int)dword_18001C010 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18001C010, 2) )
      {
        LOBYTE(cbData) = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator bool(v7);
        v11 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v16, (__int64)a2);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (__int64)&cbData,
          (__int64)&unk_1800174C0,
          v12,
          v13,
          v11);
      }
    }
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x113, v10, (const char *)v9, lpDataa);
  }
}

```

## disassembly

```asm
0x18000efb8  push    rbx
0x18000efba  push    rbp
0x18000efbb  push    rsi
0x18000efbc  push    rdi
0x18000efbd  sub     rsp, 58h
0x18000efc1  mov     r10, qword ptr [rsp+78h+arg_20]
0x18000efc9  mov     rax, rcx
0x18000efcc  mov     ecx, 0FFFFFFFFh
0x18000efd1  mov     esi, r8d
0x18000efd4  mov     rbp, rdx
0x18000efd7  cmp     r10, rcx
0x18000efda  ja      loc_18000F09E
0x18000efe0  lea     rdi, [rax+8]
0x18000efe4  mov     rcx, [rdi]
0x18000efe7  test    rcx, rcx
0x18000efea  jnz     short loc_18000EFEF
0x18000efec  mov     rcx, [rax]; hKey
0x18000efef  mov     [rsp+78h+cbData], r10d; cbData
0x18000eff4  xor     r8d, r8d; Reserved
0x18000eff7  mov     [rsp+78h+lpData], r9; lpData
0x18000effc  mov     r9d, esi; dwType
0x18000efff  call    cs:__imp_RegSetValueExW
0x18000f005  mov     ebx, eax
0x18000f007  test    eax, eax
0x18000f009  jnz     short loc_18000F014
0x18000f00b  add     rsp, 58h
0x18000f00f  pop     rdi
0x18000f010  pop     rsi
0x18000f011  pop     rbp
0x18000f012  pop     rbx
0x18000f013  retn
0x18000f014  mov     r8d, cs:dword_18001C010
0x18000f01b  mov     edx, 2
0x18000f020  cmp     r8d, edx
0x18000f023  jbe     short loc_18000F08B
0x18000f025  lea     rcx, dword_18001C010
0x18000f02c  call    _tlgKeywordOn
0x18000f031  test    al, al
0x18000f033  jz      short loc_18000F08B
0x18000f035  mov     rcx, rdi
0x18000f038  mov     [rsp+78h+var_38], ebx
0x18000f03c  mov     [rsp+78h+var_34], esi
0x18000f040  call    ??B?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBA_NXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator bool(void)
0x18000f045  mov     rdx, rbp
0x18000f048  mov     byte ptr [rsp+78h+arg_20], al
0x18000f04f  lea     rcx, [rsp+78h+var_30]
0x18000f054  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000f059  lea     rcx, [rsp+78h+var_38]
0x18000f05e  mov     [rsp+78h+var_40], rcx
0x18000f063  lea     rdx, unk_1800174C0
0x18000f06a  lea     rcx, [rsp+78h+var_34]
0x18000f06f  mov     [rsp+78h+var_48], rcx
0x18000f074  lea     rcx, [rsp+78h+arg_20]
0x18000f07c  mov     qword ptr [rsp+78h+cbData], rcx
0x18000f081  mov     [rsp+78h+lpData], rax; unsigned int
0x18000f086  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f08b  mov     rcx, [rsp+78h]; this
0x18000f090  mov     r9d, ebx; char *
0x18000f093  mov     edx, 113h; void *
0x18000f098  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000f09e  mov     rcx, [rsp+78h]; this
0x18000f0a3  mov     edx, 102h; void *
0x18000f0a8  mov     r9d, 57h ; 'W'; char *
0x18000f0ae  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
