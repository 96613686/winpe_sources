# ZtUpdateTrustedCaGlobal

- ea: `0x180011e34`
- end: `0x180011f5f`
- name: `ZtUpdateTrustedCaGlobal`
- size: `299`
- prototype: `__int64 __fastcall(int, __int64, LPVOID **)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800099a8`
- `0x18000ddec`

## callees

- `0x1800014b0`
- `0x18000dc74`
- `0x180011b68`
- `0x180011e34`
- `0x180012b20`
- `0x180015008`
- `0x1800152b0`

## import_xrefs

- `DNSAPI!DnsFreeZtTrustedCa` at `0x180011f1b`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x180011f1b`

## pseudocode

```c
__int64 __fastcall ZtUpdateTrustedCaGlobal(int a1, __int64 a2, LPVOID **a3)
{
  __int64 v4; // rbp
  LPVOID *v6; // rdi
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF

  v4 = a1;
  v10 = 0;
  v6 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_dq(1035, 0x10u, (ULONGLONG)WPP_65533a5b45023d612cc3b2c25973271a_Traceguids, a1, a2);
  if ( a3 )
    *a3 = 0;
  if ( a2 && (unsigned int)v4 <= 1 )
  {
    v8 = ZtCopyTrustedCa(a2, &v10);
    v7 = v8;
    if ( v8 )
    {
      if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
        WPP_SF_d(1035, 0x11u, (ULONGLONG)WPP_65533a5b45023d612cc3b2c25973271a_Traceguids, v8);
    }
    else
    {
      v6 = (LPVOID *)g_rgpZtTrustedCa[v4];
      g_rgpZtTrustedCa[v4] = v10;
      v10 = 0;
      if ( a3 )
      {
        *a3 = v6;
        v6 = 0;
      }
      DnsPrint_ZtTrustedCa(g_rgpZtTrustedCa[v4]);
    }
  }
  else
  {
    v7 = 87;
  }
  if ( g_fVelocityZtdnsApiRefactor )
    ZtFreeTrustedCa(v6);
  else
    DnsFreeZtTrustedCa(v6);
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x12u, (ULONGLONG)WPP_65533a5b45023d612cc3b2c25973271a_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180011e34  mov     [rsp+arg_18], rbx
0x180011e39  push    rbp
0x180011e3a  push    rsi
0x180011e3b  push    rdi
0x180011e3c  sub     rsp, 40h
0x180011e40  mov     rax, cs:__security_cookie
0x180011e47  xor     rax, rsp
0x180011e4a  mov     [rsp+58h+var_20], rax
0x180011e4f  mov     rsi, r8
0x180011e52  movsxd  rbp, ecx
0x180011e55  mov     rbx, rdx
0x180011e58  mov     [rsp+58h+var_28], 0
0x180011e61  xor     edi, edi
0x180011e63  test    byte ptr cs:xmmword_18001F260+1, 8
0x180011e6a  jz      short loc_180011E88
0x180011e6c  lea     edx, [rdi+10h]
0x180011e6f  mov     [rsp+58h+var_38], rbx
0x180011e74  mov     ecx, 40Bh
0x180011e79  lea     r8, WPP_65533a5b45023d612cc3b2c25973271a_Traceguids
0x180011e80  mov     r9d, ebp
0x180011e83  call    WPP_SF_dq
0x180011e88  test    rsi, rsi
0x180011e8b  jz      short loc_180011E90
0x180011e8d  mov     [rsi], rdi
0x180011e90  test    rbx, rbx
0x180011e93  jnz     short loc_180011E9C
0x180011e95  mov     ebx, 57h ; 'W'
0x180011e9a  jmp     short loc_180011F08
0x180011e9c  cmp     ebp, 1
0x180011e9f  ja      short loc_180011E95
0x180011ea1  lea     rdx, [rsp+58h+var_28]
0x180011ea6  mov     rcx, rbx
0x180011ea9  call    ZtCopyTrustedCa
0x180011eae  mov     ebx, eax
0x180011eb0  test    eax, eax
0x180011eb2  jnz     short loc_180011EE6
0x180011eb4  mov     rcx, [rsp+58h+var_28]
0x180011eb9  lea     rdx, g_rgpZtTrustedCa
0x180011ec0  mov     rdi, [rdx+rbp*8]
0x180011ec4  mov     [rdx+rbp*8], rcx
0x180011ec8  mov     [rsp+58h+var_28], 0
0x180011ed1  test    rsi, rsi
0x180011ed4  jz      short loc_180011EDB
0x180011ed6  mov     [rsi], rdi
0x180011ed9  xor     edi, edi
0x180011edb  mov     rcx, [rdx+rbp*8]
0x180011edf  call    DnsPrint_ZtTrustedCa
0x180011ee4  jmp     short loc_180011F08
0x180011ee6  test    byte ptr cs:xmmword_18001F260+1, 8
0x180011eed  jz      short loc_180011F08
0x180011eef  mov     edx, 11h
0x180011ef4  lea     r8, WPP_65533a5b45023d612cc3b2c25973271a_Traceguids
0x180011efb  mov     ecx, 40Bh
0x180011f00  mov     r9d, eax
0x180011f03  call    WPP_SF_d
0x180011f08  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180011f0f  mov     rcx, rdi; lpMem
0x180011f12  jz      short loc_180011F1B
0x180011f14  call    ZtFreeTrustedCa
0x180011f19  jmp     short loc_180011F21
0x180011f1b  call    cs:__imp_DnsFreeZtTrustedCa
0x180011f21  test    byte ptr cs:xmmword_18001F260+1, 8
0x180011f28  jz      short loc_180011F43
0x180011f2a  mov     edx, 12h
0x180011f2f  lea     r8, WPP_65533a5b45023d612cc3b2c25973271a_Traceguids
0x180011f36  mov     ecx, 40Bh
0x180011f3b  mov     r9d, ebx
0x180011f3e  call    WPP_SF_d
0x180011f43  mov     eax, ebx
0x180011f45  mov     rcx, [rsp+58h+var_20]
0x180011f4a  xor     rcx, rsp; StackCookie
0x180011f4d  call    __security_check_cookie
0x180011f52  mov     rbx, [rsp+58h+arg_18]
0x180011f57  add     rsp, 40h
0x180011f5b  pop     rdi
0x180011f5c  pop     rsi
0x180011f5d  pop     rbp
0x180011f5e  retn
```
