# JCDocumentEnd

- ea: `0x180014ad8`
- end: `0x180014d41`
- name: `JCDocumentEnd`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001283c`

## callees

- `0x180012558`
- `0x180012c34`
- `0x180014ad8`
- `0x180016940`
- `0x180016c90`
- `0x18001a874`
- `0x18001aa48`

## string_xrefs

- `0x180014bf2`: `Pscript_WinNT_Compat dup /terminate get exec\n`

## pseudocode

```c
_BOOL8 __fastcall JCDocumentEnd(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rax
  __int16 v5; // ax
  unsigned int v6; // r8d
  char *v7; // rdx
  __int64 v8; // rax

  DSCSend(a1, (const char *)0x12);
  DSCSend(a1, (const char *)0xA);
  BSendBoundingBox(a1, 9);
  DSCSend(a1, (const char *)5);
  DSCSend(a1, (const char *)6);
  v2 = *(_QWORD *)(a1 + 96);
  if ( (unsigned int)(*(_DWORD *)(v2 + 136) - 1) <= 4
    && *(_DWORD *)(v2 + 124) != 2
    && (*(int *)(a1 + 2152) >= 0 || *(_DWORD *)(a1 + 3668)) )
  {
    OPRawPortWrite(a1, "finalpage ", 0xAu);
    OPRawPortWrite(a1, "\r\n", 2u);
  }
  v3 = *(_DWORD *)(a1 + 2152);
  if ( v3 >= 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) & 0xFFFFFFFD) != 0 )
    {
      OPRawPortWrite(a1, "/Pscript_WinNT_Full /ProcSet findresource dup /terminate get exec\r\n", 0x43u);
      if ( (*(_BYTE *)(a1 + 2152) & 2) != 0 )
      {
        OPRawPortWrite(a1, "Pscript_WinNT_Compat dup /terminate get exec\r\n", 0x2Eu);
        *(_DWORD *)(a1 + 2152) &= ~2u;
      }
    }
    else
    {
      OPRawPortWrite(a1, "Pscript_WinNT_Incr dup /terminate get exec\r\n", 0x2Cu);
      if ( !*(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) )
        VMRestoreLevel1(a1);
    }
    GSSendRestoreForErrHandler(a1);
  }
  else
  {
    if ( (v3 & 0x20000000) != 0 )
    {
      OPRawPortWrite(a1, "Pscript_WinNT_Full dup /terminate get exec\r\n", 0x2Cu);
      *(_DWORD *)(a1 + 2152) &= ~0x20000000u;
    }
    OPRawPortWrite(a1, "Pscript_WinNT_Min dup /min_terminate get exec\r\n", 0x2Fu);
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) != 2 && *(int *)(a1 + 2152) >= 0 )
  {
    if ( !*(_DWORD *)(a1 + 2164) )
      DSCSend(a1, (const char *)4, *(unsigned int *)(a1 + 2172));
    DSCSend(a1, "(%%%%[LastPage]%%%%) = \r\n");
  }
  DSCSend(a1, (const char *)0x13);
  v4 = *(_QWORD *)(a1 + 96);
  if ( *(_DWORD *)(v4 + 124) != 2 )
  {
    if ( *(_DWORD *)(v4 + 124) == 3 )
      goto LABEL_29;
    v5 = *(_WORD *)(a1 + 166);
    if ( (v5 & 0xFFFD) != 0 )
    {
      if ( v5 != 4 )
        goto LABEL_29;
      v6 = 9;
      v7 = "\x1B%-12345X";
    }
    else
    {
      if ( *(char *)(a1 + 132) >= 0 )
        goto LABEL_29;
      v6 = 1;
      v7 = gstrCtlD;
    }
    OPRawPortWrite(a1, v7, v6);
LABEL_29:
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 2136) + 100LL) & 1) != 0 )
    {
      v8 = *(_QWORD *)(a1 + 2144);
      if ( *(_DWORD *)(v8 + 168) )
      {
        OPSendInvocation(a1, v8 + 168);
      }
      else if ( (*(_BYTE *)(v8 + 4) & 0x10) == 0 )
      {
        OPRawPortWrite(a1, "\x1B%-12345X@PJL EOJ\n\x1B%-12345X\n", 0x1Cu);
      }
    }
  }
  DSCSend(a1, (const char *)0x14);
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180014ad8  mov     [rsp+arg_0], rbx
0x180014add  push    r14
0x180014adf  sub     rsp, 20h
0x180014ae3  mov     edx, 12h
0x180014ae8  mov     rbx, rcx
0x180014aeb  call    DSCSend
0x180014af0  mov     edx, 0Ah
0x180014af5  mov     rcx, rbx
0x180014af8  call    DSCSend
0x180014afd  mov     edx, 9
0x180014b02  mov     rcx, rbx
0x180014b05  call    BSendBoundingBox
0x180014b0a  mov     edx, 5
0x180014b0f  mov     rcx, rbx
0x180014b12  call    DSCSend
0x180014b17  mov     edx, 6
0x180014b1c  mov     rcx, rbx
0x180014b1f  call    DSCSend
0x180014b24  mov     rcx, [rbx+60h]
0x180014b28  mov     r14d, 4
0x180014b2e  mov     eax, [rcx+88h]
0x180014b34  dec     eax
0x180014b36  cmp     eax, r14d
0x180014b39  ja      short loc_180014B7D
0x180014b3b  cmp     dword ptr [rcx+7Ch], 2
0x180014b3f  jz      short loc_180014B7D
0x180014b41  cmp     dword ptr [rbx+868h], 0
0x180014b48  jge     short loc_180014B53
0x180014b4a  cmp     dword ptr [rbx+0E54h], 0
0x180014b51  jz      short loc_180014B7D
0x180014b53  mov     r8d, 0Ah
0x180014b59  lea     rdx, PSFRAG_finalpageNup; "finalpage "
0x180014b60  mov     rcx, rbx
0x180014b63  call    OPRawPortWrite
0x180014b68  mov     r8d, 2
0x180014b6e  lea     rdx, gstrCRLF; "\r\n"
0x180014b75  mov     rcx, rbx
0x180014b78  call    OPRawPortWrite
0x180014b7d  mov     eax, [rbx+868h]
0x180014b83  test    eax, eax
0x180014b85  jns     short loc_180014BC1
0x180014b87  bt      eax, 1Dh
0x180014b8b  jnb     short loc_180014BAA
0x180014b8d  mov     r8d, 2Ch ; ','
0x180014b93  lea     rdx, PSFRAG_termfulldictMH; "Pscript_WinNT_Full dup /terminate get e"...
0x180014b9a  mov     rcx, rbx
0x180014b9d  call    OPRawPortWrite
0x180014ba2  btr     dword ptr [rbx+868h], 1Dh
0x180014baa  mov     r8d, 2Fh ; '/'
0x180014bb0  lea     rdx, PSFRAG_termminhdrdict; "Pscript_WinNT_Min dup /min_terminate ge"...
0x180014bb7  mov     rcx, rbx
0x180014bba  call    OPRawPortWrite
0x180014bbf  jmp     short loc_180014C36
0x180014bc1  mov     rax, [rbx+60h]
0x180014bc5  mov     rcx, rbx
0x180014bc8  test    dword ptr [rax+7Ch], 0FFFFFFFDh
0x180014bcf  jz      short loc_180014C0A
0x180014bd1  mov     r8d, 43h ; 'C'
0x180014bd7  lea     rdx, PSFRAG_termfulldict; "/Pscript_WinNT_Full /ProcSet findresour"...
0x180014bde  call    OPRawPortWrite
0x180014be3  test    byte ptr [rbx+868h], 2
0x180014bea  jz      short loc_180014C2E
0x180014bec  mov     r8d, 2Eh ; '.'
0x180014bf2  lea     rdx, PSFRAG_termcompatdict; "Pscript_WinNT_Compat dup /terminate get"...
0x180014bf9  mov     rcx, rbx
0x180014bfc  call    OPRawPortWrite
0x180014c01  and     dword ptr [rbx+868h], 0FFFFFFFDh
0x180014c08  jmp     short loc_180014C2E
0x180014c0a  mov     r8d, 2Ch ; ','
0x180014c10  lea     rdx, PSFRAG_termincrdict; "Pscript_WinNT_Incr dup /terminate get e"...
0x180014c17  call    OPRawPortWrite
0x180014c1c  mov     rax, [rbx+60h]
0x180014c20  cmp     dword ptr [rax+7Ch], 0
0x180014c24  jnz     short loc_180014C2E
0x180014c26  mov     rcx, rbx
0x180014c29  call    VMRestoreLevel1
0x180014c2e  mov     rcx, rbx
0x180014c31  call    GSSendRestoreForErrHandler
0x180014c36  mov     rax, [rbx+60h]
0x180014c3a  cmp     dword ptr [rax+7Ch], 2
0x180014c3e  jz      short loc_180014C73
0x180014c40  cmp     dword ptr [rbx+868h], 0
0x180014c47  jl      short loc_180014C73
0x180014c49  cmp     dword ptr [rbx+874h], 0
0x180014c50  jnz     short loc_180014C64
0x180014c52  mov     r8d, [rbx+87Ch]
0x180014c59  mov     rdx, r14
0x180014c5c  mov     rcx, rbx
0x180014c5f  call    DSCSend
0x180014c64  lea     rdx, DSC_LastPage; "(%%%%[LastPage]%%%%) = \r\n"
0x180014c6b  mov     rcx, rbx
0x180014c6e  call    DSCSend
0x180014c73  mov     edx, 13h
0x180014c78  mov     rcx, rbx
0x180014c7b  call    DSCSend
0x180014c80  mov     rax, [rbx+60h]
0x180014c84  cmp     dword ptr [rax+7Ch], 2
0x180014c88  jz      loc_180014D1D
0x180014c8e  cmp     dword ptr [rax+7Ch], 3
0x180014c92  jz      short loc_180014CD8
0x180014c94  movzx   eax, word ptr [rbx+0A6h]
0x180014c9b  mov     ecx, 0FFFDh
0x180014ca0  test    cx, ax
0x180014ca3  jz      short loc_180014CBA
0x180014ca5  cmp     ax, r14w
0x180014ca9  jnz     short loc_180014CD8
0x180014cab  mov     r8d, 9
0x180014cb1  lea     rdx, gstrTbcpEnd; "\x1B%-12345X"
0x180014cb8  jmp     short loc_180014CD0
0x180014cba  test    byte ptr [rbx+84h], 80h
0x180014cc1  jz      short loc_180014CD8
0x180014cc3  mov     r8d, 1
0x180014cc9  lea     rdx, gstrCtlD
0x180014cd0  mov     rcx, rbx
0x180014cd3  call    OPRawPortWrite
0x180014cd8  mov     rax, [rbx+858h]
0x180014cdf  test    byte ptr [rax+64h], 1
0x180014ce3  jz      short loc_180014D1D
0x180014ce5  mov     rax, [rbx+860h]
0x180014cec  lea     rdx, [rax+0A8h]
0x180014cf3  cmp     dword ptr [rdx], 0
0x180014cf6  jz      short loc_180014D02
0x180014cf8  mov     rcx, rbx
0x180014cfb  call    OPSendInvocation
0x180014d00  jmp     short loc_180014D1D
0x180014d02  test    byte ptr [rax+4], 10h
0x180014d06  jnz     short loc_180014D1D
0x180014d08  mov     r8d, 1Ch
0x180014d0e  lea     rdx, PSFRAG_JCLEnd; "\x1B%-12345X@PJL EOJ\n\x1B%-12345X\n"
0x180014d15  mov     rcx, rbx
0x180014d18  call    OPRawPortWrite
0x180014d1d  mov     edx, 14h
0x180014d22  mov     rcx, rbx
0x180014d25  call    DSCSend
0x180014d2a  xor     eax, eax
0x180014d2c  cmp     [rbx+0D70h], eax
0x180014d32  mov     rbx, [rsp+28h+arg_0]
0x180014d37  setz    al
0x180014d3a  add     rsp, 20h
0x180014d3e  pop     r14
0x180014d40  retn
```
