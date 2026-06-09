# CImpIADOSecurity::IsObjectSafe(ushort const *,ushort const *,ushort const *)

- ea: `0x1800295b0`
- end: `0x180029639`
- name: `?IsObjectSafe@CImpIADOSecurity@@UEAAHPEBG00@Z`
- size: `137`
- prototype: `int(CImpIADOSecurity *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800295b0`
- `0x180029cbc`
- `0x180029d10`
- `0x180030010`

## pseudocode

```c
_BOOL8 __fastcall CImpIADOSecurity::IsObjectSafe(
        CImpIADOSecurity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v6; // rdx

  v6 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  if ( !v6 )
    return 1;
  if ( a2 )
  {
    if ( (int)CImpIADOSecurity::securityCheck(this, a2, *((const unsigned __int16 **)this + 4)) >= 0 )
      return 1;
  }
  else if ( !(unsigned int)CImpIADOSecurity::isTrustedMachine(this, v6) )
  {
    return 1;
  }
  return a3
      && (*(unsigned int (__fastcall **)(CImpIADOSecurity *, _QWORD, _QWORD, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)this + 80LL))(
           this,
           *((_QWORD *)this + 5),
           *((_QWORD *)this + 4),
           a3,
           a4) == 0;
}

```

## disassembly

```asm
0x1800295b0  mov     [rsp+arg_0], rbx
0x1800295b5  mov     [rsp+arg_8], rsi
0x1800295ba  push    rdi
0x1800295bb  sub     rsp, 30h
0x1800295bf  mov     rax, rdx
0x1800295c2  mov     rsi, r9
0x1800295c5  mov     rdx, [rcx+20h]; unsigned __int16 *
0x1800295c9  mov     rdi, r8
0x1800295cc  mov     rbx, rcx
0x1800295cf  test    rdx, rdx
0x1800295d2  jz      short loc_1800295E8
0x1800295d4  test    rax, rax
0x1800295d7  jz      short loc_1800295FD
0x1800295d9  mov     r8, rdx; unsigned __int16 *
0x1800295dc  mov     rdx, rax; unsigned __int16 *
0x1800295df  call    ?securityCheck@CImpIADOSecurity@@AEAAJPEBG0@Z; CImpIADOSecurity::securityCheck(ushort const *,ushort const *)
0x1800295e4  test    eax, eax
0x1800295e6  js      short loc_180029606
0x1800295e8  mov     eax, 1
0x1800295ed  mov     rbx, [rsp+38h+arg_0]
0x1800295f2  mov     rsi, [rsp+38h+arg_8]
0x1800295f7  add     rsp, 30h
0x1800295fb  pop     rdi
0x1800295fc  retn
0x1800295fd  call    ?isTrustedMachine@CImpIADOSecurity@@AEAAJPEBG@Z; CImpIADOSecurity::isTrustedMachine(ushort const *)
0x180029602  test    eax, eax
0x180029604  jz      short loc_1800295E8
0x180029606  test    rdi, rdi
0x180029609  jz      short loc_180029635
0x18002960b  mov     rax, [rbx]
0x18002960e  mov     r9, rdi
0x180029611  mov     r8, [rbx+20h]
0x180029615  mov     rcx, rbx
0x180029618  mov     rdx, [rbx+28h]
0x18002961c  mov     [rsp+38h+var_18], rsi
0x180029621  mov     rax, [rax+50h]
0x180029625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002962a  xor     ecx, ecx
0x18002962c  test    eax, eax
0x18002962e  setz    cl
0x180029631  mov     eax, ecx
0x180029633  jmp     short loc_1800295ED
0x180029635  xor     eax, eax
0x180029637  jmp     short loc_1800295ED
```
