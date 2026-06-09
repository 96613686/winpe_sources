# VBSAttestationSerializePadding

- ea: `0x1400384e0`
- end: `0x1400385e8`
- name: `VBSAttestationSerializePadding`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140038160`

## callees

- `0x140003ad6`
- `0x140037b10`
- `0x140037e90`
- `0x1400384e0`

## string_xrefs

- `0x140038539`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`
- `0x1400385cd`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationSerializePadding(__int64 a1, void *a2, _DWORD *a3)
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
    v7 = 50;
    goto LABEL_18;
  }
  v4 = (unsigned int *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 8) >= 0xFFFFFFF0 )
  {
    *a3 = -1;
    v6 = -1073741675;
    v7 = 59;
LABEL_18:
    VBS_ATTEST_TRACE_ERROR_IN(
      v6,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\serialization.cxx",
      v7);
    return v6;
  }
  *a3 = *(_DWORD *)(a1 + 8) + 16;
  if ( a2 )
  {
    if ( (int)CopyULONGAdvanceDest(&v9, a1) >= 0 )
    {
      if ( (int)CopyULONGAdvanceDest(&v9, a1 + 4) >= 0 )
      {
        if ( (int)CopyULONGAdvanceDest(&v9, v4) >= 0 )
        {
          if ( (int)CopyULONGAdvanceDest(&v9, a1 + 12) >= 0 )
          {
            memcpy_0(v9, (const void *)(a1 + 16), *v4);
            return 0;
          }
          v5 = 88;
        }
        else
        {
          v5 = 83;
        }
      }
      else
      {
        v5 = 78;
      }
    }
    else
    {
      v5 = 73;
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
0x1400384e0  mov     [rsp+arg_0], rbx
0x1400384e5  mov     [rsp+arg_8], rdx
0x1400384ea  push    rdi
0x1400384eb  sub     rsp, 20h
0x1400384ef  mov     rbx, rcx
0x1400384f2  test    rcx, rcx
0x1400384f5  jz      loc_1400385C2
0x1400384fb  test    r8, r8
0x1400384fe  jz      loc_1400385C2
0x140038504  lea     rdi, [rcx+8]
0x140038508  mov     eax, [rdi]
0x14003850a  add     eax, 10h
0x14003850d  cmp     eax, 10h
0x140038510  jb      loc_1400385AE
0x140038516  mov     [r8], eax
0x140038519  test    rdx, rdx
0x14003851c  jz      loc_1400385AA
0x140038522  mov     rdx, rcx
0x140038525  lea     rcx, [rsp+28h+arg_8]
0x14003852a  call    CopyULONGAdvanceDest
0x14003852f  test    eax, eax
0x140038531  jns     short loc_14003854C
0x140038533  mov     r8d, 49h ; 'I'
0x140038539  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140038540  mov     ecx, 0C00000E5h
0x140038545  call    VBS_ATTEST_TRACE_ERROR_IN
0x14003854a  jmp     short loc_1400385AA
0x14003854c  lea     rdx, [rbx+4]
0x140038550  lea     rcx, [rsp+28h+arg_8]
0x140038555  call    CopyULONGAdvanceDest
0x14003855a  test    eax, eax
0x14003855c  jns     short loc_140038566
0x14003855e  mov     r8d, 4Eh ; 'N'
0x140038564  jmp     short loc_140038539
0x140038566  mov     rdx, rdi
0x140038569  lea     rcx, [rsp+28h+arg_8]
0x14003856e  call    CopyULONGAdvanceDest
0x140038573  test    eax, eax
0x140038575  jns     short loc_14003857F
0x140038577  mov     r8d, 53h ; 'S'
0x14003857d  jmp     short loc_140038539
0x14003857f  lea     rdx, [rbx+0Ch]
0x140038583  lea     rcx, [rsp+28h+arg_8]
0x140038588  call    CopyULONGAdvanceDest
0x14003858d  test    eax, eax
0x14003858f  jns     short loc_140038599
0x140038591  mov     r8d, 58h ; 'X'
0x140038597  jmp     short loc_140038539
0x140038599  mov     r8d, [rdi]; Size
0x14003859c  lea     rdx, [rbx+10h]; Src
0x1400385a0  mov     rcx, [rsp+28h+arg_8]; void *
0x1400385a5  call    memcpy_0
0x1400385aa  xor     ebx, ebx
0x1400385ac  jmp     short loc_1400385DB
0x1400385ae  mov     dword ptr [r8], 0FFFFFFFFh
0x1400385b5  mov     ebx, 0C0000095h
0x1400385ba  mov     r8d, 3Bh ; ';'
0x1400385c0  jmp     short loc_1400385CD
0x1400385c2  mov     ebx, 80090005h
0x1400385c7  mov     r8d, 32h ; '2'
0x1400385cd  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400385d4  mov     ecx, ebx
0x1400385d6  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400385db  mov     eax, ebx
0x1400385dd  mov     rbx, [rsp+28h+arg_0]
0x1400385e2  add     rsp, 20h
0x1400385e6  pop     rdi
0x1400385e7  retn
```
