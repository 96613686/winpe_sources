# DnsZtWriteCertHash

- ea: `0x18000d9ac`
- end: `0x18000da8a`
- name: `DnsZtWriteCertHash`
- size: `222`
- prototype: `__int64 __fastcall(__int64, wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cee8`

## callees

- `0x18000c37c`
- `0x18000d9ac`
- `0x180015008`
- `0x180015478`

## pseudocode

```c
__int64 __fastcall DnsZtWriteCertHash(__int64 a1, wchar_t **a2, unsigned __int64 *a3)
{
  unsigned int v6; // ebx
  int v7; // edx
  __int64 v8; // rbp
  __int64 v10; // [rsp+30h] [rbp-38h]

  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qqq(1035, 19, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, a1, a2, a3);
  if ( a1 && a2 && a3 )
  {
    v7 = *(_DWORD *)(a1 + 32);
    if ( *a3 >= (unsigned int)(2 * v7 + 1) )
    {
      v6 = 0;
      v8 = 0;
      if ( v7 )
      {
        do
        {
          LODWORD(v10) = *(unsigned __int8 *)(v8 + a1);
          v6 = StringCchPrintfExW(*a2, *a3, a2, a3, 0x1000u, L"%02x", v10);
          if ( v6 )
            break;
          v8 = (unsigned int)(v8 + 1);
        }
        while ( (unsigned int)v8 < *(_DWORD *)(a1 + 32) );
      }
    }
    else
    {
      v6 = 122;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 20, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000d9ac  push    rbx
0x18000d9ae  push    rbp
0x18000d9af  push    rsi
0x18000d9b0  push    rdi
0x18000d9b1  push    r14
0x18000d9b3  sub     rsp, 40h
0x18000d9b7  mov     rsi, r8
0x18000d9ba  mov     r14, rdx
0x18000d9bd  mov     rdi, rcx
0x18000d9c0  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000d9c7  jz      short loc_18000D9EC
0x18000d9c9  mov     [rsp+68h+var_40], r8
0x18000d9ce  mov     edx, 13h
0x18000d9d3  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000d9da  mov     qword ptr [rsp+68h+var_48], r14
0x18000d9df  mov     ecx, 40Bh
0x18000d9e4  mov     r9, rdi
0x18000d9e7  call    WPP_SF_qqq
0x18000d9ec  test    rdi, rdi
0x18000d9ef  jnz     short loc_18000D9F8
0x18000d9f1  mov     ebx, 57h ; 'W'
0x18000d9f6  jmp     short loc_18000DA5B
0x18000d9f8  test    r14, r14
0x18000d9fb  jz      short loc_18000D9F1
0x18000d9fd  test    rsi, rsi
0x18000da00  jz      short loc_18000D9F1
0x18000da02  mov     edx, [rdi+20h]
0x18000da05  lea     ecx, ds:1[rdx*2]
0x18000da0c  cmp     [rsi], rcx
0x18000da0f  jnb     short loc_18000DA18
0x18000da11  mov     ebx, 7Ah ; 'z'
0x18000da16  jmp     short loc_18000DA5B
0x18000da18  xor     ebx, ebx
0x18000da1a  xor     ebp, ebp
0x18000da1c  test    edx, edx
0x18000da1e  jz      short loc_18000DA5B
0x18000da20  movzx   ecx, byte ptr [rbp+rdi+0]
0x18000da25  lea     rax, a02x; "%02x"
0x18000da2c  mov     rdx, [rsi]; unsigned __int64
0x18000da2f  mov     r9, rsi; unsigned __int64 *
0x18000da32  mov     dword ptr [rsp+68h+var_38], ecx
0x18000da36  mov     r8, r14; unsigned __int16 **
0x18000da39  mov     rcx, [r14]; Buffer
0x18000da3c  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18000da41  mov     [rsp+68h+var_48], 1000h; unsigned int
0x18000da49  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000da4e  mov     ebx, eax
0x18000da50  test    eax, eax
0x18000da52  jnz     short loc_18000DA5B
0x18000da54  inc     ebp
0x18000da56  cmp     ebp, [rdi+20h]
0x18000da59  jb      short loc_18000DA20
0x18000da5b  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000da62  jz      short loc_18000DA7D
0x18000da64  mov     edx, 14h
0x18000da69  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000da70  mov     ecx, 40Bh
0x18000da75  mov     r9d, ebx
0x18000da78  call    WPP_SF_d
0x18000da7d  mov     eax, ebx
0x18000da7f  add     rsp, 40h
0x18000da83  pop     r14
0x18000da85  pop     rdi
0x18000da86  pop     rsi
0x18000da87  pop     rbp
0x18000da88  pop     rbx
0x18000da89  retn
```
