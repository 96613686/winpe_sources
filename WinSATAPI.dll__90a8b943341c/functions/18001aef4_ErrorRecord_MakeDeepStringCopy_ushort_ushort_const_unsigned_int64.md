# ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)

- ea: `0x18001aef4`
- end: `0x18001afa1`
- name: `?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z`
- size: `173`
- prototype: `static void(unsigned __int16 **, const unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001ac4c`
- `0x18001ad80`
- `0x18001afa8`
- `0x18001b068`

## callees

- `0x180003640`
- `0x180011fc0`
- `0x180012c06`
- `0x18001aef4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001af22`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af22`

## pseudocode

```c
void __fastcall ErrorRecord::MakeDeepStringCopy(unsigned __int16 **a1, const unsigned __int16 *a2, __int64 a3)
{
  void *v6; // rcx
  unsigned __int64 v7; // rax
  void *v8; // r14

  v6 = *a1;
  if ( v6 )
  {
    operator delete(v6);
    *a1 = 0;
  }
  if ( a2 )
  {
    if ( a3 == -1 )
      a3 = mlib::m_traits<unsigned short>::CStrlen(a2, 1023);
    if ( a3 )
    {
      v7 = 2 * (a3 + 1);
      if ( !is_mul_ok(a3 + 1, 2u) )
        v7 = -1;
      try
      {
        v8 = operator new[](v7);
        memcpy_0(v8, a2, 2 * a3 + 2);
        *a1 = (unsigned __int16 *)v8;
      }
      catch ( mlib::CStringTooBig )
      {
        return;
      }
      catch ( std::bad_alloc )
      {
      }
    }
  }
}

```

## disassembly

```asm
0x18001aef4  mov     rax, rsp
0x18001aef7  push    r14
0x18001aef9  sub     rsp, 30h
0x18001aefd  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18001af05  mov     [rax+8], rbx
0x18001af09  mov     [rax+10h], rsi
0x18001af0d  mov     [rax+18h], rdi
0x18001af11  mov     rbx, r8
0x18001af14  mov     rdi, rdx
0x18001af17  mov     rsi, rcx
0x18001af1a  mov     rcx, [rcx]
0x18001af1d  test    rcx, rcx
0x18001af20  jz      short loc_18001AF32
0x18001af22  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001af29  nop     dword ptr [rax+rax+00h]
0x18001af2e  and     qword ptr [rsi], 0
0x18001af32  test    rdi, rdi
0x18001af35  jz      short loc_18001AF8A
0x18001af37  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001af3b  cmp     rbx, r14
0x18001af3e  jnz     short loc_18001AF50
0x18001af40  mov     edx, 3FFh
0x18001af45  mov     rcx, rdi
0x18001af48  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x18001af4d  mov     rbx, rax
0x18001af50  test    rbx, rbx
0x18001af53  jz      short loc_18001AF8A
0x18001af55  lea     rcx, [rbx+1]
0x18001af59  mov     eax, 2
0x18001af5e  mul     rcx
0x18001af61  cmovo   rax, r14
0x18001af65  mov     rcx, rax; unsigned __int64
0x18001af68  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001af6d  mov     r14, rax
0x18001af70  lea     r8, ds:2[rbx*2]; Size
0x18001af78  mov     rdx, rdi; Src
0x18001af7b  mov     rcx, rax; void *
0x18001af7e  call    memcpy_0
0x18001af83  mov     [rsi], r14
0x18001af86  jmp     short loc_18001AF8A
0x18001af88  jmp     short $+2
0x18001af8a  mov     rbx, [rsp+38h+arg_0]
0x18001af8f  mov     rsi, [rsp+38h+arg_8]
0x18001af94  mov     rdi, [rsp+38h+arg_10]
0x18001af99  add     rsp, 30h
0x18001af9d  pop     r14
0x18001af9f  retn
```
