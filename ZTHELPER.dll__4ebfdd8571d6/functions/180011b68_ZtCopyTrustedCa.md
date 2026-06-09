# ZtCopyTrustedCa

- ea: `0x180011b68`
- end: `0x180011c9d`
- name: `ZtCopyTrustedCa`
- size: `309`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180011ca4`
- `0x180011e34`

## callees

- `0x18000dc74`
- `0x180011b68`
- `0x180012564`
- `0x180015008`
- `0x180015398`

## import_xrefs

- `DNSAPI!DnsFreeZtTrustedCa` at `0x180011c63`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x180011c63`

## pseudocode

```c
__int64 __fastcall ZtCopyTrustedCa(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rdi
  unsigned int v5; // ebx
  LPVOID v6; // rax
  __int64 i; // r8
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx

  v4 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qq(1035, 0xAu, (ULONGLONG)WPP_65533a5b45023d612cc3b2c25973271a_Traceguids, a1, a2);
  if ( a2 )
    *a2 = 0;
  if ( a1 && a2 )
  {
    v4 = Dns_Allocate(0x20u);
    if ( !v4
      || *(_DWORD *)(a1 + 24)
      && *(_QWORD *)(a1 + 16)
      && (v6 = Dns_Allocate(36LL * *(unsigned int *)(a1 + 24)), (v4[2] = v6) == 0) )
    {
      v5 = 14;
    }
    else
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 24); *(_DWORD *)(v10 + 4 * v9 + 32) = *(_DWORD *)(v8 + 4 * v9 + 32) )
      {
        v8 = *(_QWORD *)(a1 + 16);
        v9 = 9 * i;
        v10 = v4[2];
        i = (unsigned int)(i + 1);
        *(_OWORD *)(v10 + 4 * v9) = *(_OWORD *)(v8 + 4 * v9);
        *(_OWORD *)(v10 + 4 * v9 + 16) = *(_OWORD *)(v8 + 4 * v9 + 16);
      }
      *(_DWORD *)v4 = *(_DWORD *)a1;
      v4[1] = *(_QWORD *)(a1 + 8);
      *((_DWORD *)v4 + 6) = *(_DWORD *)(a1 + 24);
      *a2 = v4;
      v4 = 0;
      v5 = 0;
    }
  }
  else
  {
    v5 = 87;
  }
  if ( g_fVelocityZtdnsApiRefactor )
    ZtFreeTrustedCa(v4);
  else
    DnsFreeZtTrustedCa(v4);
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0xBu, (ULONGLONG)WPP_65533a5b45023d612cc3b2c25973271a_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180011b68  mov     [rsp+arg_0], rbx
0x180011b6d  mov     [rsp+arg_8], rsi
0x180011b72  push    rdi
0x180011b73  sub     rsp, 30h
0x180011b77  mov     rsi, rdx
0x180011b7a  mov     rbx, rcx
0x180011b7d  xor     edi, edi
0x180011b7f  test    byte ptr cs:xmmword_18001F260+1, 8
0x180011b86  jz      short loc_180011BA4
0x180011b88  lea     edx, [rdi+0Ah]
0x180011b8b  mov     [rsp+38h+var_18], rsi
0x180011b90  mov     ecx, 40Bh
0x180011b95  lea     r8, WPP_65533a5b45023d612cc3b2c25973271a_Traceguids
0x180011b9c  mov     r9, rbx
0x180011b9f  call    WPP_SF_qq
0x180011ba4  test    rsi, rsi
0x180011ba7  jz      short loc_180011BAC
0x180011ba9  mov     [rsi], rdi
0x180011bac  test    rbx, rbx
0x180011baf  jnz     short loc_180011BBB
0x180011bb1  mov     ebx, 57h ; 'W'
0x180011bb6  jmp     loc_180011C50
0x180011bbb  test    rsi, rsi
0x180011bbe  jz      short loc_180011BB1
0x180011bc0  mov     ecx, 20h ; ' '
0x180011bc5  call    Dns_Allocate
0x180011bca  mov     rdi, rax
0x180011bcd  test    rax, rax
0x180011bd0  jnz     short loc_180011BD9
0x180011bd2  mov     ebx, 0Eh
0x180011bd7  jmp     short loc_180011C50
0x180011bd9  cmp     dword ptr [rbx+18h], 0
0x180011bdd  jz      short loc_180011BFF
0x180011bdf  cmp     qword ptr [rbx+10h], 0
0x180011be4  jz      short loc_180011BFF
0x180011be6  mov     eax, [rbx+18h]
0x180011be9  lea     rcx, [rax+rax*8]
0x180011bed  shl     rcx, 2
0x180011bf1  call    Dns_Allocate
0x180011bf6  mov     [rdi+10h], rax
0x180011bfa  test    rax, rax
0x180011bfd  jz      short loc_180011BD2
0x180011bff  xor     r8d, r8d
0x180011c02  cmp     [rbx+18h], r8d
0x180011c06  jbe     short loc_180011C37
0x180011c08  mov     rax, [rbx+10h]
0x180011c0c  lea     rdx, [r8+r8*8]
0x180011c10  mov     rcx, [rdi+10h]
0x180011c14  inc     r8d
0x180011c17  movups  xmm0, xmmword ptr [rax+rdx*4]
0x180011c1b  movups  xmmword ptr [rcx+rdx*4], xmm0
0x180011c1f  movups  xmm1, xmmword ptr [rax+rdx*4+10h]
0x180011c24  movups  xmmword ptr [rcx+rdx*4+10h], xmm1
0x180011c29  mov     eax, [rax+rdx*4+20h]
0x180011c2d  mov     [rcx+rdx*4+20h], eax
0x180011c31  cmp     r8d, [rbx+18h]
0x180011c35  jb      short loc_180011C08
0x180011c37  mov     eax, [rbx]
0x180011c39  mov     [rdi], eax
0x180011c3b  mov     rax, [rbx+8]
0x180011c3f  mov     [rdi+8], rax
0x180011c43  mov     eax, [rbx+18h]
0x180011c46  mov     [rdi+18h], eax
0x180011c49  mov     [rsi], rdi
0x180011c4c  xor     edi, edi
0x180011c4e  xor     ebx, ebx
0x180011c50  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180011c57  mov     rcx, rdi; lpMem
0x180011c5a  jz      short loc_180011C63
0x180011c5c  call    ZtFreeTrustedCa
0x180011c61  jmp     short loc_180011C69
0x180011c63  call    cs:__imp_DnsFreeZtTrustedCa
0x180011c69  test    byte ptr cs:xmmword_18001F260+1, 8
0x180011c70  jz      short loc_180011C8B
0x180011c72  mov     edx, 0Bh
0x180011c77  lea     r8, WPP_65533a5b45023d612cc3b2c25973271a_Traceguids
0x180011c7e  mov     ecx, 40Bh
0x180011c83  mov     r9d, ebx
0x180011c86  call    WPP_SF_d
0x180011c8b  mov     rsi, [rsp+38h+arg_8]
0x180011c90  mov     eax, ebx
0x180011c92  mov     rbx, [rsp+38h+arg_0]
0x180011c97  add     rsp, 30h
0x180011c9b  pop     rdi
0x180011c9c  retn
```
