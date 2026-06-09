# CRegistry::GetCurrentBinaryKeyValue(ushort const *,CHString &)

- ea: `0x140012500`
- end: `0x14001260c`
- name: `?GetCurrentBinaryKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z`
- size: `268`
- prototype: `unsigned int __fastcall(HKEY *this, const unsigned __int16 *, struct CHString *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x140005810`
- `0x140006284`
- `0x1400075f8`
- `0x140010190`
- `0x140012500`
- `0x140012bc0`
- `0x140014ad0`

## pseudocode

```c
unsigned int __fastcall CRegistry::GetCurrentBinaryKeyValue(
        HKEY *this,
        const unsigned __int16 *a2,
        struct CHString *a3)
{
  unsigned int result; // eax
  __int64 i; // rbx
  unsigned int v6; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v7[3]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 v8[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v9[264]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v10[528]; // [rsp+460h] [rbp+360h] BYREF

  v7[0] = 3;
  v6 = 524;
  result = CRegistry::GetCurrentRawKeyValue((CRegistry *)this, this[1], a2, v10, v7, &v6);
  if ( !result )
  {
    StringCchCopyW(v8, 0x106u, L"\"");
    for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
    {
      StringCchPrintfW(v9, 0x104u, L"%02x", (unsigned __int8)v10[i]);
      StringCchCatW(v8, 0x106u, v9);
    }
    StringCchCatW(v8, 0x106u, L"\"");
    CHString::operator=(a3, v8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140012500  mov     [rsp-8+arg_18], rbx
0x140012505  push    rbp
0x140012506  push    rsi
0x140012507  push    rdi
0x140012508  lea     rbp, [rsp-580h]
0x140012510  sub     rsp, 680h
0x140012517  mov     rax, cs:__security_cookie
0x14001251e  xor     rax, rsp
0x140012521  mov     [rbp+590h+var_20], rax
0x140012528  lea     rax, [rsp+690h+var_660]
0x14001252d  mov     [rsp+690h+var_65C], 3
0x140012535  mov     [rsp+690h+var_668], rax; unsigned int *
0x14001253a  lea     r9, [rbp+590h+var_230]; void *
0x140012541  mov     rdi, r8
0x140012544  mov     [rsp+690h+var_660], 20Ch
0x14001254c  lea     rax, [rsp+690h+var_65C]
0x140012551  mov     r8, rdx; unsigned __int16 *
0x140012554  mov     rdx, [rcx+8]; HKEY
0x140012558  mov     [rsp+690h+var_670], rax; unsigned int *
0x14001255d  call    ?GetCurrentRawKeyValue@CRegistry@@AEAAKPEAUHKEY__@@PEBGPEAXPEAK3@Z; CRegistry::GetCurrentRawKeyValue(HKEY__ *,ushort const *,void *,ulong *,ulong *)
0x140012562  test    eax, eax
0x140012564  jnz     loc_1400125EA
0x14001256a  mov     esi, 106h
0x14001256f  lea     r8, asc_14001BCE8; "\""
0x140012576  mov     edx, esi; unsigned __int64
0x140012578  lea     rcx, [rsp+690h+var_650]; unsigned __int16 *
0x14001257d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140012582  xor     ebx, ebx
0x140012584  cmp     [rsp+690h+var_660], ebx
0x140012588  jbe     short loc_1400125C7
0x14001258a  movzx   r9d, [rbp+rbx+590h+var_230]
0x140012593  lea     r8, a02x; "%02x"
0x14001259a  mov     edx, 104h; unsigned __int64
0x14001259f  lea     rcx, [rbp+590h+var_440]; unsigned __int16 *
0x1400125a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400125ab  lea     r8, [rbp+590h+var_440]; unsigned __int16 *
0x1400125b2  mov     rdx, rsi; unsigned __int64
0x1400125b5  lea     rcx, [rsp+690h+var_650]; unsigned __int16 *
0x1400125ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400125bf  inc     ebx
0x1400125c1  cmp     ebx, [rsp+690h+var_660]
0x1400125c5  jb      short loc_14001258A
0x1400125c7  lea     r8, asc_14001BCE8; "\""
0x1400125ce  mov     rdx, rsi; unsigned __int64
0x1400125d1  lea     rcx, [rsp+690h+var_650]; unsigned __int16 *
0x1400125d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400125db  lea     rdx, [rsp+690h+var_650]; unsigned __int16 *
0x1400125e0  mov     rcx, rdi; this
0x1400125e3  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x1400125e8  xor     eax, eax
0x1400125ea  mov     rcx, [rbp+590h+var_20]
0x1400125f1  xor     rcx, rsp; StackCookie
0x1400125f4  call    __security_check_cookie
0x1400125f9  mov     rbx, [rsp+690h+arg_18]
0x140012601  add     rsp, 680h
0x140012608  pop     rdi
0x140012609  pop     rsi
0x14001260a  pop     rbp
0x14001260b  retn
```
