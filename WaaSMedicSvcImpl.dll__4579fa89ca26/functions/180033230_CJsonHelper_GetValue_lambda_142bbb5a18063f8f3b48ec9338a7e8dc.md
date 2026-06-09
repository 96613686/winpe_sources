# CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___

- ea: `0x180033230`
- end: `0x1800333d4`
- name: `CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180033664`

## callees

- `0x1800050a0`
- `0x180024360`
- `0x18002a32c`
- `0x180033230`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003338b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003338b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___(
        __int64 *a1,
        HSTRING a2,
        const unsigned __int16 ***a3)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64 **); // rbx
  __int64 v6; // rax
  int v7; // ebx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 **); // rcx
  __int64 *v9; // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64 *, HSTRING *); // rax
  const unsigned __int16 *v12; // rbx
  WaasMedic *StringRawBuffer; // rax
  unsigned __int16 **v14; // r8
  __int64 *v15; // rcx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 *v18; // [rsp+28h] [rbp-38h] BYREF
  int v19; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v20[32]; // [rsp+38h] [rbp-28h] BYREF

  string = a2;
  v18 = 0;
  v4 = *a1;
  if ( *a1 )
  {
    if ( a2 )
    {
      v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v4 + 48LL);
      v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, &string);
      v7 = v5(v4, *(_QWORD *)(v6 + 24), &v18);
    }
    else
    {
      v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))a1[1];
      if ( v8 )
        v7 = (**v8)(v8, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v18);
      else
        v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v4)(
               v4,
               &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
               &v18);
    }
    if ( v7 >= 0 )
    {
      v19 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v18 + 48))(v18, &v19);
      if ( v7 >= 0 )
      {
        if ( v19 )
        {
          if ( ((v19 - 3) & 0xFFFFFFFD) != 0 )
          {
            v7 = -2147024809;
          }
          else
          {
            v9 = v18;
            string = 0;
            v10 = *v18;
            if ( v19 == 3 )
            {
              WindowsDeleteString(0);
              v11 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v10 + 64);
            }
            else
            {
              WindowsDeleteString(0);
              v11 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v10 + 56);
            }
            string = 0;
            v7 = v11(v9, &string);
            if ( v7 >= 0 )
            {
              v12 = **a3;
              StringRawBuffer = (WaasMedic *)WindowsGetStringRawBuffer(string, 0);
              v7 = WaasMedic::SafeAllocString(StringRawBuffer, v12, v14);
            }
            WindowsDeleteString(string);
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147467261;
  }
  v15 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180033230  mov     [rsp-18h+arg_18], rbx
0x180033235  push    rbp
0x180033236  push    rsi
0x180033237  push    rdi
0x180033238  mov     rbp, rsp
0x18003323b  sub     rsp, 60h
0x18003323f  mov     rax, cs:__security_cookie
0x180033246  xor     rax, rsp
0x180033249  mov     [rbp+var_8], rax
0x18003324d  mov     rsi, r8
0x180033250  mov     [rbp+string], rdx
0x180033254  mov     [rbp+var_38], 0
0x18003325c  mov     rdi, [rcx]
0x18003325f  test    rdi, rdi
0x180033262  jz      loc_180033393
0x180033268  test    rdx, rdx
0x18003326b  jz      short loc_180033299
0x18003326d  mov     rax, [rdi]
0x180033270  mov     rbx, [rax+30h]
0x180033274  lea     rdx, [rbp+string]
0x180033278  lea     rcx, [rbp+var_28]
0x18003327c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180033281  nop
0x180033282  lea     r8, [rbp+var_38]
0x180033286  mov     rdx, [rax+18h]
0x18003328a  mov     rcx, rdi
0x18003328d  mov     rax, rbx
0x180033290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033295  mov     ebx, eax
0x180033297  jmp     short loc_1800332D7
0x180033299  mov     rcx, [rcx+8]
0x18003329d  test    rcx, rcx
0x1800332a0  jz      short loc_1800332BC
0x1800332a2  mov     rax, [rcx]
0x1800332a5  lea     r8, [rbp+var_38]
0x1800332a9  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800332b0  mov     rax, [rax]
0x1800332b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332b8  mov     ebx, eax
0x1800332ba  jmp     short loc_1800332D7
0x1800332bc  mov     rax, [rdi]
0x1800332bf  lea     r8, [rbp+var_38]
0x1800332c3  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800332ca  mov     rcx, rdi
0x1800332cd  mov     rax, [rax]
0x1800332d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332d5  mov     ebx, eax
0x1800332d7  test    ebx, ebx
0x1800332d9  js      loc_180033398
0x1800332df  mov     [rbp+var_30], 0
0x1800332e6  mov     rcx, [rbp+var_38]
0x1800332ea  mov     rax, [rcx]
0x1800332ed  lea     rdx, [rbp+var_30]
0x1800332f1  mov     rax, [rax+30h]
0x1800332f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332fa  mov     ebx, eax
0x1800332fc  test    eax, eax
0x1800332fe  js      loc_180033398
0x180033304  mov     ecx, [rbp+var_30]
0x180033307  test    ecx, ecx
0x180033309  jz      loc_180033398
0x18003330f  lea     eax, [rcx-3]
0x180033312  test    eax, 0FFFFFFFDh
0x180033317  jz      short loc_180033320
0x180033319  mov     ebx, 80070057h
0x18003331e  jmp     short loc_180033398
0x180033320  mov     rbx, [rbp+var_38]
0x180033324  mov     [rbp+string], 0
0x18003332c  mov     rdi, [rbx]
0x18003332f  cmp     ecx, 3
0x180033332  jnz     short loc_180033342
0x180033334  xor     ecx, ecx; string
0x180033336  call    cs:__imp_WindowsDeleteString
0x18003333c  mov     rax, [rdi+40h]
0x180033340  jmp     short loc_18003334E
0x180033342  xor     ecx, ecx; string
0x180033344  call    cs:__imp_WindowsDeleteString
0x18003334a  mov     rax, [rdi+38h]
0x18003334e  mov     [rbp+string], 0
0x180033356  lea     rdx, [rbp+string]
0x18003335a  mov     rcx, rbx
0x18003335d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033362  mov     ebx, eax
0x180033364  test    eax, eax
0x180033366  js      short loc_180033387
0x180033368  mov     rax, [rsi]
0x18003336b  mov     rbx, [rax]
0x18003336e  xor     edx, edx; length
0x180033370  mov     rcx, [rbp+string]; string
0x180033374  call    cs:__imp_WindowsGetStringRawBuffer
0x18003337a  mov     rdx, rbx; unsigned __int16 *
0x18003337d  mov     rcx, rax; this
0x180033380  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x180033385  mov     ebx, eax
0x180033387  mov     rcx, [rbp+string]; string
0x18003338b  call    cs:__imp_WindowsDeleteString
0x180033391  jmp     short loc_180033398
0x180033393  mov     ebx, 80004003h
0x180033398  mov     rcx, [rbp+var_38]
0x18003339c  test    rcx, rcx
0x18003339f  jz      short loc_1800333B6
0x1800333a1  mov     [rbp+var_38], 0
0x1800333a9  mov     rax, [rcx]
0x1800333ac  mov     rax, [rax+10h]
0x1800333b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333b5  nop
0x1800333b6  mov     eax, ebx
0x1800333b8  mov     rcx, [rbp+var_8]
0x1800333bc  xor     rcx, rsp; StackCookie
0x1800333bf  call    __security_check_cookie
0x1800333c4  mov     rbx, [rsp+60h+arg_18]
0x1800333cc  add     rsp, 60h
0x1800333d0  pop     rdi
0x1800333d1  pop     rsi
0x1800333d2  pop     rbp
0x1800333d3  retn
```
