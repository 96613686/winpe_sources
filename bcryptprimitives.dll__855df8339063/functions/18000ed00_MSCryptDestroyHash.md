# MSCryptDestroyHash

- ea: `0x18000ed00`
- end: `0x18000ee58`
- name: `MSCryptDestroyHash`
- size: `344`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800117d0`
- `0x180016af4`
- `0x180016db0`
- `0x180053de4`
- `0x180058a04`
- `0x18007dd2c`

## callees

- `0x18000ed00`
- `0x18000ee60`
- `0x18000ef28`
- `0x180010270`
- `0x1800593e0`

## string_xrefs

- `0x18000edf2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptDestroyHash(unsigned int *a1, __int64 a2, int a3)
{
  unsigned int v5; // ecx
  unsigned int *v6; // rcx

  if ( a1 && a1[1] == 1297303624 )
  {
    v5 = a1[2];
    if ( v5 - 131093 <= 1 )
    {
      MSCryptCustomBufferReset(a1 + 30);
      v6 = a1 + 50;
    }
    else
    {
      if ( v5 == 131095 )
      {
        SymCryptWipeAsm(*((_QWORD *)a1 + 54), a1[110]);
        if ( a1[110] > 0x40 )
          MSCryptFree(*((_QWORD *)a1 + 54));
        *((_QWORD *)a1 + 54) = 0;
        a1[110] = 0;
        SymCryptWipeAsm(*((_QWORD *)a1 + 64), a1[130]);
        if ( a1[130] > 0x40 )
          MSCryptFree(*((_QWORD *)a1 + 64));
        *((_QWORD *)a1 + 64) = 0;
        a1[130] = 0;
        goto LABEL_14;
      }
      if ( v5 != 131096 )
      {
LABEL_14:
        SymCryptWipeAsm(a1, *a1);
        return 0;
      }
      MSCryptCustomBufferReset(a1 + 92);
      v6 = a1 + 112;
    }
    MSCryptCustomBufferReset(v6);
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      a3,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      182);
  return 3221225480LL;
}

```

## disassembly

```asm
0x18000ed00  push    rbx
0x18000ed02  sub     rsp, 40h
0x18000ed06  mov     rbx, rcx
0x18000ed09  test    rcx, rcx
0x18000ed0c  jz      short loc_18000ED17
0x18000ed0e  cmp     dword ptr [rcx+4], 4D534848h
0x18000ed15  jz      short loc_18000ED40
0x18000ed17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed1e  lea     rdx, WPP_GLOBAL_Control
0x18000ed25  cmp     rcx, rdx
0x18000ed28  jz      short loc_18000ED34
0x18000ed2a  test    byte ptr [rcx+1Ch], 1
0x18000ed2e  jnz     loc_18000EDEE
0x18000ed34  mov     eax, 0C0000008h
0x18000ed39  add     rsp, 40h
0x18000ed3d  pop     rbx
0x18000ed3e  retn
0x18000ed40  mov     [rsp+48h+arg_0], rdi
0x18000ed45  mov     ecx, [rcx+8]
0x18000ed48  xor     edi, edi
0x18000ed4a  lea     eax, [rcx-20015h]
0x18000ed50  cmp     eax, 1
0x18000ed53  jbe     loc_18000EE1F
0x18000ed59  cmp     ecx, 20017h
0x18000ed5f  jnz     short loc_18000EDD1
0x18000ed61  mov     edx, [rbx+1B8h]
0x18000ed67  mov     rcx, [rbx+1B0h]
0x18000ed6e  call    SymCryptWipeAsm
0x18000ed73  cmp     dword ptr [rbx+1B8h], 40h ; '@'
0x18000ed7a  ja      loc_18000EE36
0x18000ed80  mov     [rbx+1B0h], rdi
0x18000ed87  mov     [rbx+1B8h], edi
0x18000ed8d  mov     edx, [rbx+208h]
0x18000ed93  mov     rcx, [rbx+200h]
0x18000ed9a  call    SymCryptWipeAsm
0x18000ed9f  cmp     dword ptr [rbx+208h], 40h ; '@'
0x18000eda6  ja      loc_18000EE47
0x18000edac  mov     [rbx+200h], rdi
0x18000edb3  mov     [rbx+208h], edi
0x18000edb9  mov     edx, [rbx]
0x18000edbb  mov     rcx, rbx
0x18000edbe  call    SymCryptWipeAsm
0x18000edc3  mov     eax, edi
0x18000edc5  mov     rdi, [rsp+48h+arg_0]
0x18000edca  add     rsp, 40h
0x18000edce  pop     rbx
0x18000edcf  retn
0x18000edd1  cmp     ecx, 20018h
0x18000edd7  jnz     short loc_18000EDB9
0x18000edd9  lea     rcx, [rbx+170h]
0x18000ede0  call    MSCryptCustomBufferReset
0x18000ede5  lea     rcx, [rbx+1C0h]
0x18000edec  jmp     short loc_18000EE2F
0x18000edee  mov     rcx, [rcx+10h]
0x18000edf2  lea     rdx, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000edf9  mov     [rsp+48h+var_18], 0FB6h
0x18000ee01  lea     r9, aStatus; "Status"
0x18000ee08  mov     [rsp+48h+var_20], rdx
0x18000ee0d  mov     [rsp+48h+var_28], 0C0000008h
0x18000ee15  call    WPP_SF_sDsd
0x18000ee1a  jmp     loc_18000ED34
0x18000ee1f  lea     rcx, [rbx+78h]
0x18000ee23  call    MSCryptCustomBufferReset
0x18000ee28  lea     rcx, [rbx+0C8h]
0x18000ee2f  call    MSCryptCustomBufferReset
0x18000ee34  jmp     short loc_18000EDB9
0x18000ee36  mov     rcx, [rbx+1B0h]
0x18000ee3d  call    MSCryptFree
0x18000ee42  jmp     loc_18000ED80
0x18000ee47  mov     rcx, [rbx+200h]
0x18000ee4e  call    MSCryptFree
0x18000ee53  jmp     loc_18000EDAC
```
