# HTTP_TRACING_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180023770`
- end: `0x1800239cc`
- name: `?SetConfigProperties@HTTP_TRACING_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(HTTP_TRACING_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003460`
- `0x180023770`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800238ad`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800238ad`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800237b3`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800237b3`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800239a8`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800239a8`

## pseudocode

```c
__int64 __fastcall HTTP_TRACING_CUSTOM_MAPPER::SetConfigProperties(
        HTTP_TRACING_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v8; // ebx
  unsigned int v9; // edx
  int v10; // edi
  _WORD *v11; // rdi
  int v12; // eax
  __int64 v13; // rax
  __int64 v15; // [rsp+30h] [rbp-41h] BYREF
  __int64 v16; // [rsp+38h] [rbp-39h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v18[56]; // [rsp+48h] [rbp-29h] BYREF

  v16 = 0;
  v15 = 0;
  v17 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v18);
  if ( a2 && a3 && a4 && a5 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v16);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 72LL))(v16, &v17);
      if ( v8 >= 0 )
      {
        v9 = v17;
        v10 = 0;
        if ( v17 )
        {
          while ( 1 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 96LL))(v16, v9 - v10 - 1, 0);
            if ( v8 < 0 )
              break;
            v9 = v17;
            if ( ++v10 >= v17 )
              goto LABEL_10;
          }
        }
        else
        {
LABEL_10:
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v16 + 48LL))(
                 v16,
                 L"clear",
                 &v15);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 88LL))(v16, v15, 0, 0);
            if ( v8 >= 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              v15 = 0;
              v11 = (_WORD *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3);
              if ( *v11 )
              {
                while ( 1 )
                {
                  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v16 + 48LL))(
                         v16,
                         L"add",
                         &v15);
                  if ( v8 < 0 )
                    break;
                  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _WORD *, _QWORD))(*(_QWORD *)v15 + 128LL))(
                         v15,
                         L"value",
                         v11,
                         0);
                  if ( v8 < 0 )
                    break;
                  v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v16 + 88LL))(
                          v16,
                          v15,
                          0xFFFFFFFFLL,
                          0);
                  v8 = v12;
                  if ( v12 < 0 )
                  {
                    if ( v12 != -2147024713 )
                      break;
                    v8 = 0;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                  v13 = -1;
                  v15 = 0;
                  do
                    ++v13;
                  while ( v11[v13] );
                  v11 += v13 + 1;
                  if ( !*v11 )
                    goto LABEL_25;
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
LABEL_25:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180023770  push    rbp
0x180023772  push    rbx
0x180023773  push    rsi
0x180023774  push    rdi
0x180023775  push    r14
0x180023777  push    r15
0x180023779  lea     rbp, [rsp-27h]
0x18002377e  sub     rsp, 98h
0x180023785  mov     rax, cs:__security_cookie
0x18002378c  xor     rax, rsp
0x18002378f  mov     [rbp+4Fh+var_40], rax
0x180023793  mov     rdi, [rbp+4Fh+arg_20]
0x180023797  lea     rcx, [rbp+4Fh+var_78]
0x18002379b  xor     r15d, r15d
0x18002379e  mov     rsi, r9
0x1800237a1  mov     [rbp+4Fh+var_88], r15
0x1800237a5  mov     r14, r8
0x1800237a8  mov     [rbp+4Fh+var_90], r15
0x1800237ac  mov     rbx, rdx
0x1800237af  mov     [rbp+4Fh+var_80], r15d
0x1800237b3  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800237b9  test    rbx, rbx
0x1800237bc  jz      loc_18002396D
0x1800237c2  test    r14, r14
0x1800237c5  jz      loc_18002396D
0x1800237cb  test    rsi, rsi
0x1800237ce  jz      loc_18002396D
0x1800237d4  test    rdi, rdi
0x1800237d7  jz      loc_18002396D
0x1800237dd  mov     rax, [rdi]
0x1800237e0  lea     rdx, [rbp+4Fh+var_88]
0x1800237e4  mov     rcx, rdi
0x1800237e7  mov     rax, [rax+28h]
0x1800237eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f0  mov     ebx, eax
0x1800237f2  test    eax, eax
0x1800237f4  js      loc_180023972
0x1800237fa  mov     rcx, [rbp+4Fh+var_88]
0x1800237fe  lea     rdx, [rbp+4Fh+var_80]
0x180023802  mov     rax, [rcx]
0x180023805  mov     rax, [rax+48h]
0x180023809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002380e  mov     ebx, eax
0x180023810  test    eax, eax
0x180023812  js      loc_180023972
0x180023818  mov     edx, [rbp+4Fh+var_80]
0x18002381b  mov     edi, r15d
0x18002381e  test    edx, edx
0x180023820  jz      short loc_18002384C
0x180023822  mov     rcx, [rbp+4Fh+var_88]
0x180023826  sub     edx, edi
0x180023828  dec     edx
0x18002382a  xor     r8d, r8d
0x18002382d  mov     rax, [rcx]
0x180023830  mov     rax, [rax+60h]
0x180023834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023839  mov     ebx, eax
0x18002383b  test    eax, eax
0x18002383d  js      loc_180023972
0x180023843  mov     edx, [rbp+4Fh+var_80]
0x180023846  inc     edi
0x180023848  cmp     edi, edx
0x18002384a  jb      short loc_180023822
0x18002384c  mov     rcx, [rbp+4Fh+var_88]
0x180023850  lea     r8, [rbp+4Fh+var_90]
0x180023854  lea     rdx, aClear; "clear"
0x18002385b  mov     rax, [rcx]
0x18002385e  mov     rax, [rax+30h]
0x180023862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023867  mov     ebx, eax
0x180023869  test    eax, eax
0x18002386b  js      loc_180023972
0x180023871  mov     rcx, [rbp+4Fh+var_88]
0x180023875  xor     r9d, r9d
0x180023878  mov     rdx, [rbp+4Fh+var_90]
0x18002387c  xor     r8d, r8d
0x18002387f  mov     rax, [rcx]
0x180023882  mov     rax, [rax+58h]
0x180023886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002388b  mov     ebx, eax
0x18002388d  test    eax, eax
0x18002388f  js      loc_180023972
0x180023895  mov     rcx, [rbp+4Fh+var_90]
0x180023899  mov     rax, [rcx]
0x18002389c  mov     rax, [rax+10h]
0x1800238a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238a5  lea     rcx, [r14+10h]
0x1800238a9  mov     [rbp+4Fh+var_90], r15
0x1800238ad  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800238b3  mov     rdi, [rax+18h]
0x1800238b7  cmp     [rdi], r15w
0x1800238bb  jz      loc_180023972
0x1800238c1  mov     rcx, [rbp+4Fh+var_88]
0x1800238c5  lea     r8, [rbp+4Fh+var_90]
0x1800238c9  lea     rdx, aAdd; "add"
0x1800238d0  mov     rax, [rcx]
0x1800238d3  mov     rax, [rax+30h]
0x1800238d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238dc  mov     ebx, eax
0x1800238de  test    eax, eax
0x1800238e0  js      loc_180023972
0x1800238e6  mov     rcx, [rbp+4Fh+var_90]
0x1800238ea  lea     rdx, aValue; "value"
0x1800238f1  xor     r9d, r9d
0x1800238f4  mov     r8, rdi
0x1800238f7  mov     rax, [rcx]
0x1800238fa  mov     rax, [rax+80h]
0x180023901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023906  mov     ebx, eax
0x180023908  test    eax, eax
0x18002390a  js      short loc_180023972
0x18002390c  mov     rcx, [rbp+4Fh+var_88]
0x180023910  xor     r9d, r9d
0x180023913  mov     rdx, [rbp+4Fh+var_90]
0x180023917  or      r8d, 0FFFFFFFFh
0x18002391b  mov     rax, [rcx]
0x18002391e  mov     rax, [rax+58h]
0x180023922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023927  mov     ebx, eax
0x180023929  test    eax, eax
0x18002392b  jns     short loc_180023937
0x18002392d  cmp     eax, 800700B7h
0x180023932  jnz     short loc_180023972
0x180023934  mov     ebx, r15d
0x180023937  mov     rcx, [rbp+4Fh+var_90]
0x18002393b  mov     rax, [rcx]
0x18002393e  mov     rax, [rax+10h]
0x180023942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023947  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002394b  mov     [rbp+4Fh+var_90], r15
0x18002394f  inc     rax
0x180023952  cmp     [rdi+rax*2], r15w
0x180023957  jnz     short loc_18002394F
0x180023959  lea     rdi, [rdi+rax*2]
0x18002395d  add     rdi, 2
0x180023961  cmp     [rdi], r15w
0x180023965  jnz     loc_1800238C1
0x18002396b  jmp     short loc_18002398B
0x18002396d  mov     ebx, 80070057h
0x180023972  mov     rcx, [rbp+4Fh+var_90]
0x180023976  test    rcx, rcx
0x180023979  jz      short loc_18002398B
0x18002397b  mov     rax, [rcx]
0x18002397e  mov     rax, [rax+10h]
0x180023982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023987  mov     [rbp+4Fh+var_90], r15
0x18002398b  mov     rcx, [rbp+4Fh+var_88]
0x18002398f  test    rcx, rcx
0x180023992  jz      short loc_1800239A4
0x180023994  mov     rax, [rcx]
0x180023997  mov     rax, [rax+10h]
0x18002399b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239a0  mov     [rbp+4Fh+var_88], r15
0x1800239a4  lea     rcx, [rbp+4Fh+var_78]
0x1800239a8  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800239ae  mov     eax, ebx
0x1800239b0  mov     rcx, [rbp+4Fh+var_40]
0x1800239b4  xor     rcx, rsp; StackCookie
0x1800239b7  call    __security_check_cookie
0x1800239bc  add     rsp, 98h
0x1800239c3  pop     r15
0x1800239c5  pop     r14
0x1800239c7  pop     rdi
0x1800239c8  pop     rsi
0x1800239c9  pop     rbx
0x1800239ca  pop     rbp
0x1800239cb  retn
```
