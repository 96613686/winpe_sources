# CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___

- ea: `0x18002de0c`
- end: `0x18002dfb0`
- name: `CJsonHelper::_GetValue__lambda_142bbb5a18063f8f3b48ec9338a7e8dc___`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f140`
- `0x18002e294`

## callees

- `0x180003bb0`
- `0x180023798`
- `0x180024ff0`
- `0x18002de0c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002df50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002df50`

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
0x18002de0c  mov     [rsp-18h+arg_18], rbx
0x18002de11  push    rbp
0x18002de12  push    rsi
0x18002de13  push    rdi
0x18002de14  mov     rbp, rsp
0x18002de17  sub     rsp, 60h
0x18002de1b  mov     rax, cs:__security_cookie
0x18002de22  xor     rax, rsp
0x18002de25  mov     [rbp+var_8], rax
0x18002de29  mov     rsi, r8
0x18002de2c  mov     [rbp+string], rdx
0x18002de30  mov     [rbp+var_38], 0
0x18002de38  mov     rdi, [rcx]
0x18002de3b  test    rdi, rdi
0x18002de3e  jz      loc_18002DF6F
0x18002de44  test    rdx, rdx
0x18002de47  jz      short loc_18002DE75
0x18002de49  mov     rax, [rdi]
0x18002de4c  mov     rbx, [rax+30h]
0x18002de50  lea     rdx, [rbp+string]
0x18002de54  lea     rcx, [rbp+var_28]
0x18002de58  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002de5d  nop
0x18002de5e  lea     r8, [rbp+var_38]
0x18002de62  mov     rdx, [rax+18h]
0x18002de66  mov     rcx, rdi
0x18002de69  mov     rax, rbx
0x18002de6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de71  mov     ebx, eax
0x18002de73  jmp     short loc_18002DEB3
0x18002de75  mov     rcx, [rcx+8]
0x18002de79  test    rcx, rcx
0x18002de7c  jz      short loc_18002DE98
0x18002de7e  mov     rax, [rcx]
0x18002de81  lea     r8, [rbp+var_38]
0x18002de85  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18002de8c  mov     rax, [rax]
0x18002de8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de94  mov     ebx, eax
0x18002de96  jmp     short loc_18002DEB3
0x18002de98  mov     rax, [rdi]
0x18002de9b  lea     r8, [rbp+var_38]
0x18002de9f  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18002dea6  mov     rcx, rdi
0x18002dea9  mov     rax, [rax]
0x18002deac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deb1  mov     ebx, eax
0x18002deb3  test    ebx, ebx
0x18002deb5  js      loc_18002DF74
0x18002debb  mov     [rbp+var_30], 0
0x18002dec2  mov     rcx, [rbp+var_38]
0x18002dec6  mov     rax, [rcx]
0x18002dec9  lea     rdx, [rbp+var_30]
0x18002decd  mov     rax, [rax+30h]
0x18002ded1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ded6  mov     ebx, eax
0x18002ded8  test    eax, eax
0x18002deda  js      loc_18002DF74
0x18002dee0  mov     ecx, [rbp+var_30]
0x18002dee3  test    ecx, ecx
0x18002dee5  jz      loc_18002DF74
0x18002deeb  lea     eax, [rcx-3]
0x18002deee  test    eax, 0FFFFFFFDh
0x18002def3  jz      short loc_18002DEFC
0x18002def5  mov     ebx, 80070057h
0x18002defa  jmp     short loc_18002DF74
0x18002defc  mov     rbx, [rbp+var_38]
0x18002df00  mov     [rbp+string], 0
0x18002df08  mov     rdi, [rbx]
0x18002df0b  cmp     ecx, 3
0x18002df0e  jnz     short loc_18002DF1E
0x18002df10  xor     ecx, ecx; string
0x18002df12  call    cs:__imp_WindowsDeleteString
0x18002df18  mov     rax, [rdi+40h]
0x18002df1c  jmp     short loc_18002DF2A
0x18002df1e  xor     ecx, ecx; string
0x18002df20  call    cs:__imp_WindowsDeleteString
0x18002df26  mov     rax, [rdi+38h]
0x18002df2a  mov     [rbp+string], 0
0x18002df32  lea     rdx, [rbp+string]
0x18002df36  mov     rcx, rbx
0x18002df39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df3e  mov     ebx, eax
0x18002df40  test    eax, eax
0x18002df42  js      short loc_18002DF63
0x18002df44  mov     rax, [rsi]
0x18002df47  mov     rbx, [rax]
0x18002df4a  xor     edx, edx; length
0x18002df4c  mov     rcx, [rbp+string]; string
0x18002df50  call    cs:__imp_WindowsGetStringRawBuffer
0x18002df56  mov     rdx, rbx; unsigned __int16 *
0x18002df59  mov     rcx, rax; this
0x18002df5c  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x18002df61  mov     ebx, eax
0x18002df63  mov     rcx, [rbp+string]; string
0x18002df67  call    cs:__imp_WindowsDeleteString
0x18002df6d  jmp     short loc_18002DF74
0x18002df6f  mov     ebx, 80004003h
0x18002df74  mov     rcx, [rbp+var_38]
0x18002df78  test    rcx, rcx
0x18002df7b  jz      short loc_18002DF92
0x18002df7d  mov     [rbp+var_38], 0
0x18002df85  mov     rax, [rcx]
0x18002df88  mov     rax, [rax+10h]
0x18002df8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df91  nop
0x18002df92  mov     eax, ebx
0x18002df94  mov     rcx, [rbp+var_8]
0x18002df98  xor     rcx, rsp; StackCookie
0x18002df9b  call    __security_check_cookie
0x18002dfa0  mov     rbx, [rsp+60h+arg_18]
0x18002dfa8  add     rsp, 60h
0x18002dfac  pop     rdi
0x18002dfad  pop     rsi
0x18002dfae  pop     rbp
0x18002dfaf  retn
```
