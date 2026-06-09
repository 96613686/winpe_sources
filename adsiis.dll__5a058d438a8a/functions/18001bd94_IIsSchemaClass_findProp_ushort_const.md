# IIsSchemaClass::findProp(ushort const *)

- ea: `0x18001bd94`
- end: `0x18001be4f`
- name: `?findProp@IIsSchemaClass@@QEAAJPEBG@Z`
- size: `187`
- prototype: `int(IIsSchemaClass *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001bc84`

## callees

- `0x18001bd94`
- `0x18001be58`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001bde5`
- `msvcrt!_wcsicmp` at `0x18001be19`
- `msvcrt!_wcsicmp` at `0x18001bde5`
- `msvcrt!_wcsicmp` at `0x18001be19`

## pseudocode

```c
__int64 __fastcall IIsSchemaClass::findProp(IIsSchemaClass *this, const unsigned __int16 *a2, unsigned __int64 a3)
{
  unsigned __int16 *v3; // rdi
  unsigned __int16 *v6; // rbx
  wchar_t String1[264]; // [rsp+20h] [rbp-238h] BYREF

  v3 = (unsigned __int16 *)*((_QWORD *)this + 7);
  while ( 1 )
  {
    v3 = grabProp(String1, v3, a3);
    if ( !v3 )
      break;
    if ( String1[0] && !_wcsicmp(String1, a2) )
      return 0;
  }
  v6 = (unsigned __int16 *)*((_QWORD *)this + 6);
  while ( 1 )
  {
    v6 = grabProp(String1, v6, a3);
    if ( !v6 )
      break;
    if ( String1[0] && !_wcsicmp(String1, a2) )
      return 0;
  }
  return 2147504134LL;
}

```

## disassembly

```asm
0x18001bd94  mov     [rsp+arg_10], rbx
0x18001bd99  push    rbp
0x18001bd9a  push    rsi
0x18001bd9b  push    rdi
0x18001bd9c  sub     rsp, 240h
0x18001bda3  mov     rax, cs:__security_cookie
0x18001bdaa  xor     rax, rsp
0x18001bdad  mov     [rsp+258h+var_28], rax
0x18001bdb5  mov     rdi, [rcx+38h]
0x18001bdb9  mov     rsi, rdx
0x18001bdbc  mov     rbx, rcx
0x18001bdbf  xor     ebp, ebp
0x18001bdc1  mov     rdx, rdi; unsigned __int16 *
0x18001bdc4  lea     rcx, [rsp+258h+String1]; unsigned __int16 *
0x18001bdc9  call    ?grabProp@@YAPEAGPEAG0_K@Z; grabProp(ushort *,ushort *,unsigned __int64)
0x18001bdce  mov     rdi, rax
0x18001bdd1  test    rax, rax
0x18001bdd4  jz      short loc_18001BDF1
0x18001bdd6  cmp     [rsp+258h+String1], bp
0x18001bddb  jz      short loc_18001BDC1
0x18001bddd  mov     rdx, rsi; String2
0x18001bde0  lea     rcx, [rsp+258h+String1]; String1
0x18001bde5  call    cs:__imp__wcsicmp
0x18001bdeb  test    eax, eax
0x18001bded  jnz     short loc_18001BDC1
0x18001bdef  jmp     short loc_18001BE23
0x18001bdf1  mov     rbx, [rbx+30h]
0x18001bdf5  mov     rdx, rbx; unsigned __int16 *
0x18001bdf8  lea     rcx, [rsp+258h+String1]; unsigned __int16 *
0x18001bdfd  call    ?grabProp@@YAPEAGPEAG0_K@Z; grabProp(ushort *,ushort *,unsigned __int64)
0x18001be02  mov     rbx, rax
0x18001be05  test    rax, rax
0x18001be08  jz      short loc_18001BE27
0x18001be0a  cmp     [rsp+258h+String1], bp
0x18001be0f  jz      short loc_18001BDF5
0x18001be11  mov     rdx, rsi; String2
0x18001be14  lea     rcx, [rsp+258h+String1]; String1
0x18001be19  call    cs:__imp__wcsicmp
0x18001be1f  test    eax, eax
0x18001be21  jnz     short loc_18001BDF5
0x18001be23  xor     eax, eax
0x18001be25  jmp     short loc_18001BE2C
0x18001be27  mov     eax, 80005006h
0x18001be2c  mov     rcx, [rsp+258h+var_28]
0x18001be34  xor     rcx, rsp; StackCookie
0x18001be37  call    __security_check_cookie
0x18001be3c  mov     rbx, [rsp+258h+arg_10]
0x18001be44  add     rsp, 240h
0x18001be4b  pop     rdi
0x18001be4c  pop     rsi
0x18001be4d  pop     rbp
0x18001be4e  retn
```
