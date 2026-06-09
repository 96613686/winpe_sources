# SCRIPT_MAP_CUSTOM_MAPPER::CreateNewNameForHandler(INativeConfigurationElement *)

- ea: `0x18001c02c`
- end: `0x18001c18b`
- name: `?CreateNewNameForHandler@SCRIPT_MAP_CUSTOM_MAPPER@@AEAAJPEAVINativeConfigurationElement@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(SCRIPT_MAP_CUSTOM_MAPPER *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180024a10`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18001c02c`
- `0x18002c010`

## import_xrefs

- `msvcrt!_ultow` at `0x18001c0f9`
- `msvcrt!_ultow` at `0x18001c0f9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c0d3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c0d3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001c083`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001c083`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c161`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001c161`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c13c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001c13c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c10b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c121`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c10b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001c121`

## pseudocode

```c
__int64 __fastcall SCRIPT_MAP_CUSTOM_MAPPER::CreateNewNameForHandler(
        SCRIPT_MAP_CUSTOM_MAPPER *this,
        struct INativeConfigurationElement *a2)
{
  int v4; // ebx
  unsigned int v5; // ecx
  __int64 (__fastcall *v6)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  const unsigned __int16 *v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[56]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[64]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v12[256]; // [rsp+F0h] [rbp-10h] BYREF

  v9 = 0;
  memset_0(v12, 0, sizeof(v12));
  STRU::STRU((STRU *)v10, v12, 0x100u);
  if ( a2 )
  {
    v4 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
           a2,
           L"name",
           &v9,
           0,
           0);
    if ( v4 >= 0 )
    {
      v4 = STRU::Copy((STRU *)v10, v9);
      if ( v4 >= 0 )
      {
        v5 = *((_DWORD *)this + 514);
        *((_DWORD *)this + 514) = v5 + 1;
        _ultow(v5, Buffer, 10);
        v4 = STRU::Append((STRU *)v10, L"-");
        if ( v4 >= 0 )
        {
          v4 = STRU::Append((STRU *)v10, Buffer);
          if ( v4 >= 0 )
          {
            v6 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)a2 + 128LL);
            Str = STRU::QueryStr((STRU *)v10);
            v4 = v6(a2, L"name", Str, 0);
          }
        }
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c02c  mov     [rsp-8+arg_10], rbx
0x18001c031  push    rbp
0x18001c032  push    rsi
0x18001c033  push    rdi
0x18001c034  lea     rbp, [rsp-200h]
0x18001c03c  sub     rsp, 300h
0x18001c043  mov     rax, cs:__security_cookie
0x18001c04a  xor     rax, rsp
0x18001c04d  mov     [rbp+210h+var_20], rax
0x18001c054  mov     rdi, rdx
0x18001c057  mov     [rsp+310h+var_2E0], 0
0x18001c060  mov     rsi, rcx
0x18001c063  xor     edx, edx; Val
0x18001c065  lea     rcx, [rbp+210h+var_220]; void *
0x18001c069  mov     r8d, 200h; Size
0x18001c06f  call    memset_0
0x18001c074  mov     r8d, 100h
0x18001c07a  lea     rdx, [rbp+210h+var_220]
0x18001c07e  lea     rcx, [rsp+310h+var_2D8]
0x18001c083  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001c089  test    rdi, rdi
0x18001c08c  jnz     short loc_18001C098
0x18001c08e  mov     ebx, 80070057h
0x18001c093  jmp     loc_18001C15C
0x18001c098  mov     rax, [rdi]
0x18001c09b  lea     r8, [rsp+310h+var_2E0]
0x18001c0a0  xor     r9d, r9d
0x18001c0a3  mov     [rsp+310h+var_2F0], 0
0x18001c0ac  lea     rdx, aName; "name"
0x18001c0b3  mov     rcx, rdi
0x18001c0b6  mov     rax, [rax+40h]
0x18001c0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0bf  mov     ebx, eax
0x18001c0c1  test    eax, eax
0x18001c0c3  js      loc_18001C15C
0x18001c0c9  mov     rdx, [rsp+310h+var_2E0]
0x18001c0ce  lea     rcx, [rsp+310h+var_2D8]
0x18001c0d3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001c0d9  mov     ebx, eax
0x18001c0db  test    eax, eax
0x18001c0dd  js      short loc_18001C15C
0x18001c0df  mov     ecx, [rsi+808h]; Value
0x18001c0e5  lea     rdx, [rsp+310h+Buffer]; Buffer
0x18001c0ea  mov     r8d, 0Ah; Radix
0x18001c0f0  lea     eax, [rcx+1]
0x18001c0f3  mov     [rsi+808h], eax
0x18001c0f9  call    cs:__imp__ultow
0x18001c0ff  lea     rdx, asc_180034320; "-"
0x18001c106  lea     rcx, [rsp+310h+var_2D8]
0x18001c10b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001c111  mov     ebx, eax
0x18001c113  test    eax, eax
0x18001c115  js      short loc_18001C15C
0x18001c117  lea     rdx, [rsp+310h+Buffer]
0x18001c11c  lea     rcx, [rsp+310h+var_2D8]
0x18001c121  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001c127  mov     ebx, eax
0x18001c129  test    eax, eax
0x18001c12b  js      short loc_18001C15C
0x18001c12d  mov     rax, [rdi]
0x18001c130  lea     rcx, [rsp+310h+var_2D8]
0x18001c135  mov     rbx, [rax+80h]
0x18001c13c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001c142  xor     r9d, r9d
0x18001c145  lea     rdx, aName; "name"
0x18001c14c  mov     r8, rax
0x18001c14f  mov     rcx, rdi
0x18001c152  mov     rax, rbx
0x18001c155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c15a  mov     ebx, eax
0x18001c15c  lea     rcx, [rsp+310h+var_2D8]
0x18001c161  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001c167  mov     eax, ebx
0x18001c169  mov     rcx, [rbp+210h+var_20]
0x18001c170  xor     rcx, rsp; StackCookie
0x18001c173  call    __security_check_cookie
0x18001c178  mov     rbx, [rsp+310h+arg_10]
0x18001c180  add     rsp, 300h
0x18001c187  pop     rdi
0x18001c188  pop     rsi
0x18001c189  pop     rbp
0x18001c18a  retn
```
