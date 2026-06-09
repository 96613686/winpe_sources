# CServiceProvider::Validate(void)

- ea: `0x18000b9b4`
- end: `0x18000bae1`
- name: `?Validate@CServiceProvider@@IEAAJXZ`
- size: `301`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000ad60`

## callees

- `0x18000b9b4`
- `0x18000bce4`
- `0x18000bd30`
- `0x180014010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18000ba72`
- `ole32!PropVariantClear` at `0x18000ba72`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Validate(CServiceProvider *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  int v4; // eax
  bool v5; // cf
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  v2 = *((_QWORD *)this + 11);
  v9 = 0;
  v8 = 0;
  *(_OWORD *)pvar = 0;
  if ( !v2
    || (v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v2 + 48LL))(v2, 0, &v9)) == 0
    && (v3 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v9 + 40LL))(
               v9,
               &PKEY_PNPX_GlobalIdentity,
               pvar)) == 0
    && (LOWORD(pvar[0]) != 31 || !pvar[1]) )
  {
    v3 = -2147024809;
  }
  PropVariantClear(pvar);
  v4 = 0;
  if ( v3 )
    v5 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v5 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v4) = !v5;
    if ( v4 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return v3;
}

```

## disassembly

```asm
0x18000b9b4  mov     [rsp+arg_8], rbx
0x18000b9b9  mov     [rsp+arg_10], rsi
0x18000b9be  push    rdi
0x18000b9bf  sub     rsp, 50h
0x18000b9c3  mov     rdi, rcx
0x18000b9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9cd  lea     rsi, WPP_GLOBAL_Control
0x18000b9d4  cmp     rcx, rsi
0x18000b9d7  jz      short loc_18000B9F9
0x18000b9d9  cmp     byte ptr [rcx+19h], 4
0x18000b9dd  jb      short loc_18000B9F9
0x18000b9df  mov     rcx, [rcx+10h]
0x18000b9e3  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000b9ea  mov     edx, 1Ch
0x18000b9ef  mov     [rsp+58h+var_38], rdi
0x18000b9f4  call    WPP_SF_sq
0x18000b9f9  mov     rcx, [rdi+58h]
0x18000b9fd  xor     eax, eax
0x18000b9ff  mov     [rsp+58h+arg_0], 0
0x18000ba08  xorps   xmm0, xmm0
0x18000ba0b  mov     [rsp+58h+var_18], rax
0x18000ba10  movups  xmmword ptr [rsp+58h+pvar], xmm0
0x18000ba15  test    rcx, rcx
0x18000ba18  jz      short loc_18000BA68
0x18000ba1a  mov     rax, [rcx]
0x18000ba1d  lea     r8, [rsp+58h+arg_0]
0x18000ba22  xor     edx, edx
0x18000ba24  mov     rax, [rax+30h]
0x18000ba28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba2d  mov     ebx, eax
0x18000ba2f  test    eax, eax
0x18000ba31  jnz     short loc_18000BA6D
0x18000ba33  mov     rcx, [rsp+58h+arg_0]
0x18000ba38  lea     r8, [rsp+58h+pvar]
0x18000ba3d  lea     rdx, PKEY_PNPX_GlobalIdentity
0x18000ba44  mov     rax, [rcx]
0x18000ba47  mov     rax, [rax+28h]
0x18000ba4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba50  mov     ebx, eax
0x18000ba52  test    eax, eax
0x18000ba54  jnz     short loc_18000BA6D
0x18000ba56  lea     eax, [rbx+1Fh]
0x18000ba59  cmp     ax, word ptr [rsp+58h+pvar]
0x18000ba5e  jnz     short loc_18000BA68
0x18000ba60  cmp     [rsp+58h+pvar+8], 0
0x18000ba66  jnz     short loc_18000BA6D
0x18000ba68  mov     ebx, 80070057h
0x18000ba6d  lea     rcx, [rsp+58h+pvar]; pvar
0x18000ba72  call    cs:__imp_PropVariantClear
0x18000ba78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba7f  xor     eax, eax
0x18000ba81  test    ebx, ebx
0x18000ba83  jnz     short loc_18000BA8B
0x18000ba85  cmp     byte ptr [rcx+19h], 4
0x18000ba89  jmp     short loc_18000BA8F
0x18000ba8b  cmp     byte ptr [rcx+19h], 2
0x18000ba8f  setnb   al
0x18000ba92  cmp     rcx, rsi
0x18000ba95  jz      short loc_18000BAB9
0x18000ba97  test    eax, eax
0x18000ba99  jz      short loc_18000BAB9
0x18000ba9b  mov     rcx, [rcx+10h]
0x18000ba9f  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x18000baa6  mov     edx, 1Dh
0x18000baab  mov     [rsp+58h+var_30], ebx
0x18000baaf  mov     [rsp+58h+var_38], rdi
0x18000bab4  call    WPP_SF_sqd
0x18000bab9  mov     rcx, [rsp+58h+arg_0]
0x18000babe  test    rcx, rcx
0x18000bac1  jz      short loc_18000BACF
0x18000bac3  mov     rax, [rcx]
0x18000bac6  mov     rax, [rax+10h]
0x18000baca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bacf  mov     rsi, [rsp+58h+arg_10]
0x18000bad4  mov     eax, ebx
0x18000bad6  mov     rbx, [rsp+58h+arg_8]
0x18000badb  add     rsp, 50h
0x18000badf  pop     rdi
0x18000bae0  retn
```
