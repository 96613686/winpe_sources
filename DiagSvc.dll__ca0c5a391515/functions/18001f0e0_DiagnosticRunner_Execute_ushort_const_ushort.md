# DiagnosticRunner::Execute(ushort const *,ushort * *)

- ea: `0x18001f0e0`
- end: `0x18001f2b3`
- name: `?Execute@DiagnosticRunner@@MEAAJPEBGPEAPEAG@Z`
- size: `467`
- prototype: `__int64 __fastcall(DiagnosticRunner *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003b84`
- `0x18001f0e0`
- `0x180024bc8`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001f239`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f29d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f239`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f29d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f280`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f28a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f280`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f28a`

## string_xrefs

- `0x18001f296`: `<?xml version="1.0"?><Rootcauses Version="1.0"><Rootcause><Resolutions><Resolution></Resolution></Resolutions></Rootcause></Rootcauses>`

## pseudocode

```c
__int64 __fastcall DiagnosticRunner::Execute(DiagnosticRunner *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v6; // ebx
  OLECHAR *v7; // rax
  InteractionClient *v8; // rax
  BSTR bstrString[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+78h] [rbp+38h] BYREF
  __int64 v12; // [rsp+80h] [rbp+40h] BYREF
  OLECHAR *psz; // [rsp+88h] [rbp+48h] BYREF

  if ( a2 )
  {
    v6 = (*(__int64 (__fastcall **)(DiagnosticRunner *))(*(_QWORD *)this + 96LL))(this);
    if ( v6 >= 0 )
    {
      bstrString[0] = 0;
      v12 = 0;
      v11 = 0;
      psz = 0;
      v7 = (OLECHAR *)operator new(0x10u);
      bstrString[1] = v7;
      if ( v7 && (v8 = InteractionClient::InteractionClient((InteractionClient *)v7)) != 0 )
      {
        v6 = (**(__int64 (__fastcall ***)(InteractionClient *, GUID *, __int64 *))v8)(v8, &IID_IUnknown, &v12);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(DiagnosticRunner *, const unsigned __int16 *, BSTR *))(*(_QWORD *)this + 104LL))(
                 this,
                 a2,
                 bstrString);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(DiagnosticRunner *, __int64 *))(*(_QWORD *)this + 88LL))(this, &v11);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(DiagnosticRunner *, __int64, BSTR, __int64, _QWORD))(*(_QWORD *)this
                                                                                                 + 112LL))(
                     this,
                     v11,
                     bstrString[0],
                     v12,
                     0);
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(DiagnosticRunner *, __int64, OLECHAR **))(*(_QWORD *)this + 128LL))(
                       this,
                       v11,
                       &psz);
                if ( v6 >= 0 )
                  v6 = (*(__int64 (__fastcall **)(DiagnosticRunner *, __int64, OLECHAR *))(*(_QWORD *)this + 136LL))(
                         this,
                         v11,
                         psz);
              }
            }
          }
        }
      }
      else
      {
        v6 = -2147024882;
      }
      if ( a3 )
        *a3 = SysAllocString(psz);
      if ( v11 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v11 = 0;
      }
      if ( v12 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v12 = 0;
      }
      SysFreeString(psz);
      SysFreeString(bstrString[0]);
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( !*a3 )
    *a3 = SysAllocString(
            L"<?xml version=\"1.0\"?><Rootcauses Version=\"1.0\"><Rootcause><Resolutions><Resolution></Resolution></Resolu"
             "tions></Rootcause></Rootcauses>");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f0e0  push    rbp
0x18001f0e2  push    rbx
0x18001f0e3  push    rsi
0x18001f0e4  push    rdi
0x18001f0e5  push    r14
0x18001f0e7  mov     rbp, rsp
0x18001f0ea  sub     rsp, 40h
0x18001f0ee  mov     rsi, r8
0x18001f0f1  mov     r14, rdx
0x18001f0f4  mov     rdi, rcx
0x18001f0f7  test    rdx, rdx
0x18001f0fa  jnz     short loc_18001F106
0x18001f0fc  mov     ebx, 80070057h
0x18001f101  jmp     loc_18001F290
0x18001f106  mov     rax, [rcx]
0x18001f109  mov     rax, [rax+60h]
0x18001f10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f112  mov     ebx, eax
0x18001f114  test    eax, eax
0x18001f116  js      loc_18001F290
0x18001f11c  mov     ecx, 10h; Size
0x18001f121  mov     [rbp+bstrString], 0
0x18001f129  mov     [rbp+arg_10], 0
0x18001f131  mov     [rbp+arg_8], 0
0x18001f139  mov     [rbp+psz], 0
0x18001f141  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f146  mov     [rbp+var_8], rax
0x18001f14a  test    rax, rax
0x18001f14d  jz      loc_18001F22B
0x18001f153  mov     rcx, rax; this
0x18001f156  call    ??0InteractionClient@@QEAA@XZ; InteractionClient::InteractionClient(void)
0x18001f15b  mov     r9, rax
0x18001f15e  test    rax, rax
0x18001f161  jz      loc_18001F22B
0x18001f167  mov     rcx, [rax]
0x18001f16a  lea     r8, [rbp+arg_10]
0x18001f16e  lea     rdx, IID_IUnknown
0x18001f175  mov     rax, [rcx]
0x18001f178  mov     rcx, r9
0x18001f17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f180  mov     ebx, eax
0x18001f182  test    eax, eax
0x18001f184  js      loc_18001F230
0x18001f18a  mov     rax, [rdi]
0x18001f18d  lea     r8, [rbp+bstrString]
0x18001f191  mov     rdx, r14
0x18001f194  mov     rcx, rdi
0x18001f197  mov     rax, [rax+68h]
0x18001f19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1a0  mov     ebx, eax
0x18001f1a2  test    eax, eax
0x18001f1a4  js      loc_18001F230
0x18001f1aa  mov     rax, [rdi]
0x18001f1ad  lea     rdx, [rbp+arg_8]
0x18001f1b1  mov     rcx, rdi
0x18001f1b4  mov     rax, [rax+58h]
0x18001f1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1bd  mov     ebx, eax
0x18001f1bf  test    eax, eax
0x18001f1c1  js      short loc_18001F230
0x18001f1c3  mov     rax, [rdi]
0x18001f1c6  mov     rcx, rdi
0x18001f1c9  mov     r9, [rbp+arg_10]
0x18001f1cd  mov     r8, [rbp+bstrString]
0x18001f1d1  mov     rdx, [rbp+arg_8]
0x18001f1d5  mov     rax, [rax+70h]
0x18001f1d9  mov     [rsp+40h+var_20], 0
0x18001f1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1e7  mov     ebx, eax
0x18001f1e9  test    eax, eax
0x18001f1eb  js      short loc_18001F230
0x18001f1ed  mov     rax, [rdi]
0x18001f1f0  lea     r8, [rbp+psz]
0x18001f1f4  mov     rdx, [rbp+arg_8]
0x18001f1f8  mov     rcx, rdi
0x18001f1fb  mov     rax, [rax+80h]
0x18001f202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f207  mov     ebx, eax
0x18001f209  test    eax, eax
0x18001f20b  js      short loc_18001F230
0x18001f20d  mov     rax, [rdi]
0x18001f210  mov     rcx, rdi
0x18001f213  mov     r8, [rbp+psz]
0x18001f217  mov     rdx, [rbp+arg_8]
0x18001f21b  mov     rax, [rax+88h]
0x18001f222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f227  mov     ebx, eax
0x18001f229  jmp     short loc_18001F230
0x18001f22b  mov     ebx, 8007000Eh
0x18001f230  test    rsi, rsi
0x18001f233  jz      short loc_18001F242
0x18001f235  mov     rcx, [rbp+psz]; psz
0x18001f239  call    cs:__imp_SysAllocString
0x18001f23f  mov     [rsi], rax
0x18001f242  mov     rcx, [rbp+arg_8]
0x18001f246  test    rcx, rcx
0x18001f249  jz      short loc_18001F25F
0x18001f24b  mov     rax, [rcx]
0x18001f24e  mov     rax, [rax+10h]
0x18001f252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f257  mov     [rbp+arg_8], 0
0x18001f25f  mov     rcx, [rbp+arg_10]
0x18001f263  test    rcx, rcx
0x18001f266  jz      short loc_18001F27C
0x18001f268  mov     rax, [rcx]
0x18001f26b  mov     rax, [rax+10h]
0x18001f26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f274  mov     [rbp+arg_10], 0
0x18001f27c  mov     rcx, [rbp+psz]; bstrString
0x18001f280  call    cs:__imp_SysFreeString
0x18001f286  mov     rcx, [rbp+bstrString]; bstrString
0x18001f28a  call    cs:__imp_SysFreeString
0x18001f290  cmp     qword ptr [rsi], 0
0x18001f294  jnz     short loc_18001F2A6
0x18001f296  lea     rcx, aXmlVersion10Ro; "<?xml version=\"1.0\"?><Rootcauses Vers"...
0x18001f29d  call    cs:__imp_SysAllocString
0x18001f2a3  mov     [rsi], rax
0x18001f2a6  mov     eax, ebx
0x18001f2a8  add     rsp, 40h
0x18001f2ac  pop     r14
0x18001f2ae  pop     rdi
0x18001f2af  pop     rsi
0x18001f2b0  pop     rbx
0x18001f2b1  pop     rbp
0x18001f2b2  retn
```
