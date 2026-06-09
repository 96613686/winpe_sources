# WP_OBJECT::Create(void)

- ea: `0x18001e418`
- end: `0x18001e585`
- name: `?Create@WP_OBJECT@@QEAAJXZ`
- size: `365`
- prototype: `__int64 __fastcall(WP_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001e590`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180005ba8`
- `0x18001e418`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_ultow` at `0x18001e4bf`
- `msvcrt!_ultow` at `0x18001e4bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e546`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e546`

## pseudocode

```c
__int64 __fastcall WP_OBJECT::Create(WP_OBJECT *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  int v4; // ebx
  unsigned int Value; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v8[32]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v9; // [rsp+50h] [rbp-B0h]
  int v10; // [rsp+58h] [rbp-A8h]
  __int16 v11; // [rsp+5Ch] [rbp-A4h]
  int v12; // [rsp+60h] [rbp-A0h]
  wchar_t Buffer[64]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v14; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v15[510]; // [rsp+F2h] [rbp-Eh] BYREF

  Value = 0;
  pv = 0;
  memset_0(v15, 0, sizeof(v15));
  v2 = (__int64 *)*((_QWORD *)this + 27);
  v9 = (unsigned __int16 *)&v14;
  v10 = 512;
  v14 = 0;
  v3 = *v2;
  v11 = 256;
  v12 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v3 + 24))(v2, &Value);
  if ( v4 >= 0 )
  {
    _ultow(Value, Buffer, 10);
    v4 = COMMAND_OBJECT::AddAttribute(this, L"WP.NAME", Buffer);
    if ( v4 >= 0 )
    {
      v4 = STRU::Copy((STRU *)v8, Buffer);
      if ( v4 >= 0 )
      {
        v4 = STRU::Copy((WP_OBJECT *)((char *)this + 16), v9);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 27) + 56LL))(
                 *((_QWORD *)this + 27),
                 &pv);
          if ( v4 >= 0 )
            v4 = COMMAND_OBJECT::AddAttribute(this, L"APPPOOL.NAME", (const unsigned __int16 *)pv);
        }
      }
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001e418  mov     [rsp-8+arg_8], rbx
0x18001e41d  mov     [rsp-8+arg_10], rdi
0x18001e422  push    rbp
0x18001e423  lea     rbp, [rsp-200h]
0x18001e42b  sub     rsp, 300h
0x18001e432  mov     rax, cs:__security_cookie
0x18001e439  xor     rax, rsp
0x18001e43c  mov     [rbp+200h+var_10], rax
0x18001e443  mov     rdi, rcx
0x18001e446  mov     [rsp+300h+Value], 0
0x18001e44e  lea     rcx, [rbp+200h+var_20E]; void *
0x18001e452  mov     [rsp+300h+pv], 0
0x18001e45b  xor     edx, edx; Val
0x18001e45d  mov     r8d, 1FEh; Size
0x18001e463  call    memset_0
0x18001e468  mov     rcx, [rdi+0D8h]
0x18001e46f  lea     rax, [rbp+200h+var_210]
0x18001e473  mov     [rsp+300h+var_2B0], rax
0x18001e478  lea     rdx, [rsp+300h+Value]
0x18001e47d  xor     eax, eax
0x18001e47f  mov     [rsp+300h+var_2A8], 200h
0x18001e487  mov     [rbp+200h+var_210], ax
0x18001e48b  mov     rax, [rcx]
0x18001e48e  mov     [rsp+300h+var_2A4], 100h
0x18001e495  mov     [rsp+300h+var_2A0], 0
0x18001e49d  mov     rax, [rax+18h]
0x18001e4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4a6  mov     ebx, eax
0x18001e4a8  test    eax, eax
0x18001e4aa  js      loc_18001E53C
0x18001e4b0  mov     ecx, [rsp+300h+Value]; Value
0x18001e4b4  lea     rdx, [rsp+300h+Buffer]; Buffer
0x18001e4b9  mov     r8d, 0Ah; Radix
0x18001e4bf  call    cs:__imp__ultow
0x18001e4c5  lea     r8, [rsp+300h+Buffer]; unsigned __int16 *
0x18001e4ca  mov     rcx, rdi; this
0x18001e4cd  lea     rdx, aWpName_0; "WP.NAME"
0x18001e4d4  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001e4d9  mov     ebx, eax
0x18001e4db  test    eax, eax
0x18001e4dd  js      short loc_18001E53C
0x18001e4df  lea     rdx, [rsp+300h+Buffer]; unsigned __int16 *
0x18001e4e4  lea     rcx, [rsp+300h+var_2D0]; this
0x18001e4e9  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001e4ee  mov     ebx, eax
0x18001e4f0  test    eax, eax
0x18001e4f2  js      short loc_18001E53C
0x18001e4f4  mov     rdx, [rsp+300h+var_2B0]; unsigned __int16 *
0x18001e4f9  lea     rcx, [rdi+10h]; this
0x18001e4fd  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001e502  mov     ebx, eax
0x18001e504  test    eax, eax
0x18001e506  js      short loc_18001E53C
0x18001e508  mov     rcx, [rdi+0D8h]
0x18001e50f  lea     rdx, [rsp+300h+pv]
0x18001e514  mov     rax, [rcx]
0x18001e517  mov     rax, [rax+38h]
0x18001e51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e520  mov     ebx, eax
0x18001e522  test    eax, eax
0x18001e524  js      short loc_18001E53C
0x18001e526  mov     r8, [rsp+300h+pv]; unsigned __int16 *
0x18001e52b  lea     rdx, aApppoolName; "APPPOOL.NAME"
0x18001e532  mov     rcx, rdi; this
0x18001e535  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18001e53a  mov     ebx, eax
0x18001e53c  mov     rcx, [rsp+300h+pv]; pv
0x18001e541  test    rcx, rcx
0x18001e544  jz      short loc_18001E555
0x18001e546  call    cs:__imp_CoTaskMemFree
0x18001e54c  mov     [rsp+300h+pv], 0
0x18001e555  lea     rcx, [rsp+300h+var_2D0]; this
0x18001e55a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001e55f  mov     eax, ebx
0x18001e561  mov     rcx, [rbp+200h+var_10]
0x18001e568  xor     rcx, rsp; StackCookie
0x18001e56b  call    __security_check_cookie
0x18001e570  lea     r11, [rsp+300h+var_s0]
0x18001e578  mov     rbx, [r11+18h]
0x18001e57c  mov     rdi, [r11+20h]
0x18001e580  mov     rsp, r11
0x18001e583  pop     rbp
0x18001e584  retn
```
