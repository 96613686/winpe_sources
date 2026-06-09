# VBSAttestationSerializeClaimAttributes

- ea: `0x140038074`
- end: `0x14003815a`
- name: `VBSAttestationSerializeClaimAttributes`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140037bec`
- `0x140038160`

## callees

- `0x140003ad6`
- `0x140037b10`
- `0x140037e90`
- `0x140038074`

## string_xrefs

- `0x1400380c5`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`
- `0x14003813f`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationSerializeClaimAttributes(__int64 a1, void *a2, _DWORD *a3)
{
  unsigned int *v4; // rdi
  __int64 v5; // r8
  unsigned int v6; // ebx
  __int64 v7; // r8
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = a2;
  if ( !a1 || !a3 )
  {
    v6 = -2146893819;
    v7 = 117;
    goto LABEL_16;
  }
  v4 = (unsigned int *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 8) >= 0xFFFFFFF4 )
  {
    *a3 = -1;
    v6 = -1073741675;
    v7 = 126;
LABEL_16:
    VBS_ATTEST_TRACE_ERROR_IN(
      v6,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\serialization.cxx",
      v7);
    return v6;
  }
  *a3 = *(_DWORD *)(a1 + 8) + 12;
  if ( a2 )
  {
    if ( (int)CopyULONGAdvanceDest(&v9, a1) >= 0 )
    {
      if ( (int)CopyULONGAdvanceDest(&v9, a1 + 4) >= 0 )
      {
        if ( (int)CopyULONGAdvanceDest(&v9, v4) >= 0 )
        {
          memcpy_0(v9, (const void *)(a1 + 12), *v4);
          return 0;
        }
        v5 = 150;
      }
      else
      {
        v5 = 145;
      }
    }
    else
    {
      v5 = 140;
    }
    VBS_ATTEST_TRACE_ERROR_IN(
      3221225701LL,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\serialization.cxx",
      v5);
  }
  return 0;
}

```

## disassembly

```asm
0x140038074  mov     [rsp+arg_0], rbx
0x140038079  mov     [rsp+arg_8], rdx
0x14003807e  push    rdi
0x14003807f  sub     rsp, 20h
0x140038083  mov     rbx, rcx
0x140038086  test    rcx, rcx
0x140038089  jz      loc_140038134
0x14003808f  test    r8, r8
0x140038092  jz      loc_140038134
0x140038098  lea     rdi, [rcx+8]
0x14003809c  mov     eax, [rdi]
0x14003809e  add     eax, 0Ch
0x1400380a1  cmp     eax, 0Ch
0x1400380a4  jb      short loc_140038120
0x1400380a6  mov     [r8], eax
0x1400380a9  test    rdx, rdx
0x1400380ac  jz      short loc_14003811C
0x1400380ae  mov     rdx, rcx
0x1400380b1  lea     rcx, [rsp+28h+arg_8]
0x1400380b6  call    CopyULONGAdvanceDest
0x1400380bb  test    eax, eax
0x1400380bd  jns     short loc_1400380D8
0x1400380bf  mov     r8d, 8Ch
0x1400380c5  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400380cc  mov     ecx, 0C00000E5h
0x1400380d1  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400380d6  jmp     short loc_14003811C
0x1400380d8  lea     rdx, [rbx+4]
0x1400380dc  lea     rcx, [rsp+28h+arg_8]
0x1400380e1  call    CopyULONGAdvanceDest
0x1400380e6  test    eax, eax
0x1400380e8  jns     short loc_1400380F2
0x1400380ea  mov     r8d, 91h
0x1400380f0  jmp     short loc_1400380C5
0x1400380f2  mov     rdx, rdi
0x1400380f5  lea     rcx, [rsp+28h+arg_8]
0x1400380fa  call    CopyULONGAdvanceDest
0x1400380ff  test    eax, eax
0x140038101  jns     short loc_14003810B
0x140038103  mov     r8d, 96h
0x140038109  jmp     short loc_1400380C5
0x14003810b  mov     r8d, [rdi]; Size
0x14003810e  lea     rdx, [rbx+0Ch]; Src
0x140038112  mov     rcx, [rsp+28h+arg_8]; void *
0x140038117  call    memcpy_0
0x14003811c  xor     ebx, ebx
0x14003811e  jmp     short loc_14003814D
0x140038120  mov     dword ptr [r8], 0FFFFFFFFh
0x140038127  mov     ebx, 0C0000095h
0x14003812c  mov     r8d, 7Eh ; '~'
0x140038132  jmp     short loc_14003813F
0x140038134  mov     ebx, 80090005h
0x140038139  mov     r8d, 75h ; 'u'
0x14003813f  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140038146  mov     ecx, ebx
0x140038148  call    VBS_ATTEST_TRACE_ERROR_IN
0x14003814d  mov     eax, ebx
0x14003814f  mov     rbx, [rsp+28h+arg_0]
0x140038154  add     rsp, 20h
0x140038158  pop     rdi
0x140038159  retn
```
