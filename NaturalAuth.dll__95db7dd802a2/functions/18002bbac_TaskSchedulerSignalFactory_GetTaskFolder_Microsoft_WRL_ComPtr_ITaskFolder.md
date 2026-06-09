# TaskSchedulerSignalFactory::GetTaskFolder(Microsoft::WRL::ComPtr<ITaskFolder> *)

- ea: `0x18002bbac`
- end: `0x18002bd07`
- name: `?GetTaskFolder@TaskSchedulerSignalFactory@@AEAAJPEAV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a584`
- `0x18002a978`

## callees

- `0x180014e7c`
- `0x18001fb2c`
- `0x18002072c`
- `0x180029630`
- `0x18002bbac`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18002bcd3`
- `OLEAUT32!__imp_VariantClear` at `0x18002bcd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TaskSchedulerSignalFactory::GetTaskFolder(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, _QWORD *, __int64); // r14
  _QWORD *v6; // rdx
  int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, _QWORD *, __int128 *, __int64); // rdi
  _variant_t *v12; // rax
  __int128 v13; // xmm6
  __int64 v14; // xmm7_8
  _QWORD *v15; // rdx
  __int128 v17; // [rsp+38h] [rbp-19h] BYREF
  __int64 v18; // [rsp+48h] [rbp-9h]
  VARIANTARG pvarg; // [rsp+58h] [rbp+7h] BYREF
  __int64 v20; // [rsp+B8h] [rbp+67h] BYREF
  char v21; // [rsp+C0h] [rbp+6Fh] BYREF

  v4 = *(_QWORD *)(a1 + 8);
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)v4 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  v6 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v20, L"\\Microsoft\\Windows\\NaturalAuthentication");
  if ( v6 )
    v6 = (_QWORD *)*v6;
  v7 = v5(v4, v6, a2);
  _bstr_t::_Free((_bstr_t *)&v20);
  if ( v7 == -2147024894 )
  {
    v20 = 0;
    v8 = *(_QWORD *)(a1 + 8);
    v9 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v8 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v7 = v9(v8, L"\\", &v20);
    if ( v7 >= 0 )
    {
      v10 = v20;
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, __int64))(*(_QWORD *)v20 + 88LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
      v12 = _variant_t::_variant_t((_variant_t *)&pvarg, L"O:BAG:BAD:(A;CI;FA;;;BA)");
      v13 = *(_OWORD *)v12;
      v14 = *((_QWORD *)v12 + 2);
      v15 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v21, L"\\Microsoft\\Windows\\NaturalAuthentication");
      if ( v15 )
        v15 = (_QWORD *)*v15;
      v17 = v13;
      v18 = v14;
      v7 = v11(v10, v15, &v17, a2);
      _bstr_t::_Free((_bstr_t *)&v21);
      VariantClear(&pvarg);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002bbac  mov     rax, rsp
0x18002bbaf  mov     [rax+18h], rbx
0x18002bbb3  mov     [rax+20h], rsi
0x18002bbb7  push    rbp
0x18002bbb8  push    rdi
0x18002bbb9  push    r14
0x18002bbbb  lea     rbp, [rax-5Fh]
0x18002bbbf  sub     rsp, 90h
0x18002bbc6  movaps  xmmword ptr [rax-28h], xmm6
0x18002bbca  movaps  xmmword ptr [rax-38h], xmm7
0x18002bbce  mov     rsi, rdx
0x18002bbd1  mov     rdi, rcx
0x18002bbd4  mov     rbx, [rcx+8]
0x18002bbd8  mov     rax, [rbx]
0x18002bbdb  mov     r14, [rax+38h]
0x18002bbdf  mov     rcx, rdx
0x18002bbe2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bbe7  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\NaturalAuthentica"...
0x18002bbee  lea     rcx, [rbp+57h+arg_0]; this
0x18002bbf2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002bbf7  nop
0x18002bbf8  mov     rdx, [rax]
0x18002bbfb  test    rdx, rdx
0x18002bbfe  jz      short loc_18002BC03
0x18002bc00  mov     rdx, [rdx]
0x18002bc03  mov     r8, rsi
0x18002bc06  mov     rcx, rbx
0x18002bc09  mov     rax, r14
0x18002bc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc11  mov     ebx, eax
0x18002bc13  lea     rcx, [rbp+57h+arg_0]; this
0x18002bc17  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002bc1c  cmp     ebx, 80070002h
0x18002bc22  jnz     loc_18002BCE3
0x18002bc28  mov     [rbp+57h+arg_0], 0
0x18002bc30  mov     rdi, [rdi+8]
0x18002bc34  mov     rax, [rdi]
0x18002bc37  mov     rbx, [rax+38h]
0x18002bc3b  lea     rcx, [rbp+57h+arg_0]
0x18002bc3f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bc44  lea     r8, [rbp+57h+arg_0]
0x18002bc48  lea     rdx, asc_18004AA98; "\\"
0x18002bc4f  mov     rcx, rdi
0x18002bc52  mov     rax, rbx
0x18002bc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc5a  mov     ebx, eax
0x18002bc5c  test    eax, eax
0x18002bc5e  js      short loc_18002BCDA
0x18002bc60  mov     rbx, [rbp+57h+arg_0]
0x18002bc64  mov     rax, [rbx]
0x18002bc67  mov     rdi, [rax+58h]
0x18002bc6b  mov     rcx, rsi
0x18002bc6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bc73  lea     rdx, aOBagBadACiFaBa; "O:BAG:BAD:(A;CI;FA;;;BA)"
0x18002bc7a  lea     rcx, [rbp+57h+pvarg]; this
0x18002bc7e  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18002bc83  nop
0x18002bc84  movups  xmm6, xmmword ptr [rax]
0x18002bc87  movsd   xmm7, qword ptr [rax+10h]
0x18002bc8c  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\NaturalAuthentica"...
0x18002bc93  lea     rcx, [rbp+57h+arg_8]; this
0x18002bc97  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002bc9c  nop
0x18002bc9d  mov     rdx, [rax]
0x18002bca0  test    rdx, rdx
0x18002bca3  jz      short loc_18002BCA8
0x18002bca5  mov     rdx, [rdx]
0x18002bca8  movaps  [rbp+57h+var_70], xmm6
0x18002bcac  movsd   [rbp+57h+var_60], xmm7
0x18002bcb1  mov     r9, rsi
0x18002bcb4  lea     r8, [rbp+57h+var_70]
0x18002bcb8  mov     rcx, rbx
0x18002bcbb  mov     rax, rdi
0x18002bcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcc3  mov     ebx, eax
0x18002bcc5  lea     rcx, [rbp+57h+arg_8]; this
0x18002bcc9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002bcce  nop
0x18002bccf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002bcd3  call    cs:__imp_VariantClear
0x18002bcd9  nop
0x18002bcda  lea     rcx, [rbp+57h+arg_0]
0x18002bcde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bce3  mov     eax, ebx
0x18002bce5  lea     r11, [rsp+0A0h+var_10]
0x18002bced  mov     rbx, [r11+30h]
0x18002bcf1  mov     rsi, [r11+38h]
0x18002bcf5  movaps  xmm6, xmmword ptr [r11-10h]
0x18002bcfa  movaps  xmm7, [rsp+0A0h+var_38+8]
0x18002bcff  mov     rsp, r11
0x18002bd02  pop     r14
0x18002bd04  pop     rdi
0x18002bd05  pop     rbp
0x18002bd06  retn
```
