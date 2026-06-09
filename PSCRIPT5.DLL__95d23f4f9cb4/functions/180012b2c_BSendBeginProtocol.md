# BSendBeginProtocol

- ea: `0x180012b2c`
- end: `0x180012c2e`
- name: `BSendBeginProtocol`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014988`

## callees

- `0x180012b2c`
- `0x1800138e4`
- `0x180016940`
- `0x180016c90`

## pseudocode

```c
_BOOL8 __fastcall BSendBeginProtocol(__int64 a1)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int16 v5; // ax
  unsigned int v6; // r8d
  char *v7; // rdx

  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) == 2 )
    return 1;
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 2136) + 100LL) & 1) != 0 )
  {
    v3 = *(_QWORD *)(a1 + 2144);
    if ( *(_DWORD *)(v3 + 152) )
    {
      OPSendInvocation(a1, v3 + 152);
    }
    else if ( (*(_BYTE *)(v3 + 4) & 4) == 0 )
    {
      OPRawPortWrite(a1, "\x1B%-12345X@PJL JOB\n", 0x12u);
    }
    BSendFeatures(a1, 1);
    v4 = *(_QWORD *)(a1 + 2144);
    if ( *(_DWORD *)(v4 + 160) )
    {
      OPSendInvocation(a1, v4 + 160);
    }
    else if ( (*(_BYTE *)(v4 + 4) & 8) == 0 )
    {
      OPRawPortWrite(a1, "@PJL ENTER LANGUAGE=POSTSCRIPT\n", 0x1Fu);
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) != 3 )
  {
    v5 = *(_WORD *)(a1 + 166);
    if ( (v5 & 0xFFFD) != 0 )
    {
      if ( v5 == 4 )
      {
        v6 = 2;
        v7 = (char *)&gstrCtlAM;
LABEL_18:
        OPRawPortWrite(a1, v7, v6);
      }
    }
    else if ( (*(_BYTE *)(a1 + 132) & 0x40) != 0 )
    {
      v6 = 1;
      v7 = gstrCtlD;
      goto LABEL_18;
    }
  }
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180012b2c  push    rbx
0x180012b2e  sub     rsp, 20h
0x180012b32  mov     rax, [rcx+60h]
0x180012b36  mov     rbx, rcx
0x180012b39  cmp     dword ptr [rax+7Ch], 2
0x180012b3d  jnz     short loc_180012B49
0x180012b3f  mov     eax, 1
0x180012b44  jmp     loc_180012C28
0x180012b49  mov     rax, [rcx+858h]
0x180012b50  test    byte ptr [rax+64h], 1
0x180012b54  jz      short loc_180012BCF
0x180012b56  mov     rax, [rcx+860h]
0x180012b5d  lea     rdx, [rax+98h]
0x180012b64  cmp     dword ptr [rdx], 0
0x180012b67  jz      short loc_180012B70
0x180012b69  call    OPSendInvocation
0x180012b6e  jmp     short loc_180012B88
0x180012b70  test    byte ptr [rax+4], 4
0x180012b74  jnz     short loc_180012B88
0x180012b76  mov     r8d, 12h
0x180012b7c  lea     rdx, PSFRAG_JCLBegin; "\x1B%-12345X@PJL JOB\n"
0x180012b83  call    OPRawPortWrite
0x180012b88  xor     r8d, r8d
0x180012b8b  mov     rcx, rbx
0x180012b8e  lea     edx, [r8+1]
0x180012b92  call    BSendFeatures
0x180012b97  mov     rax, [rbx+860h]
0x180012b9e  lea     rdx, [rax+0A0h]
0x180012ba5  cmp     dword ptr [rdx], 0
0x180012ba8  jz      short loc_180012BB4
0x180012baa  mov     rcx, rbx
0x180012bad  call    OPSendInvocation
0x180012bb2  jmp     short loc_180012BCF
0x180012bb4  test    byte ptr [rax+4], 8
0x180012bb8  jnz     short loc_180012BCF
0x180012bba  mov     r8d, 1Fh
0x180012bc0  lea     rdx, PSFRAG_JCLEnterPS; "@PJL ENTER LANGUAGE=POSTSCRIPT\n"
0x180012bc7  mov     rcx, rbx
0x180012bca  call    OPRawPortWrite
0x180012bcf  mov     rax, [rbx+60h]
0x180012bd3  cmp     dword ptr [rax+7Ch], 3
0x180012bd7  jz      short loc_180012C1D
0x180012bd9  movzx   eax, word ptr [rbx+0A6h]
0x180012be0  mov     ecx, 0FFFDh
0x180012be5  test    cx, ax
0x180012be8  jz      short loc_180012BFF
0x180012bea  cmp     ax, 4
0x180012bee  jnz     short loc_180012C1D
0x180012bf0  mov     r8d, 2
0x180012bf6  lea     rdx, gstrCtlAM
0x180012bfd  jmp     short loc_180012C15
0x180012bff  test    byte ptr [rbx+84h], 40h
0x180012c06  jz      short loc_180012C1D
0x180012c08  mov     r8d, 1
0x180012c0e  lea     rdx, gstrCtlD
0x180012c15  mov     rcx, rbx
0x180012c18  call    OPRawPortWrite
0x180012c1d  xor     eax, eax
0x180012c1f  cmp     [rbx+0D70h], eax
0x180012c25  setz    al
0x180012c28  add     rsp, 20h
0x180012c2c  pop     rbx
0x180012c2d  retn
```
