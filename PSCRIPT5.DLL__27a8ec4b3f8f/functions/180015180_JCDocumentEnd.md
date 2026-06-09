# JCDocumentEnd

- ea: `0x180015180`
- end: `0x1800153ea`
- name: `JCDocumentEnd`
- size: `618`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012e18`

## callees

- `0x180012b2c`
- `0x180013220`
- `0x180015180`
- `0x1800170a0`
- `0x1800173f8`
- `0x18001b1b4`
- `0x18001b388`

## string_xrefs

- `0x18001529a`: `Pscript_WinNT_Compat dup /terminate get exec\n`

## pseudocode

```c
_BOOL8 __fastcall JCDocumentEnd(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rax
  __int16 v5; // ax
  __int64 v6; // rax

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
    if ( *(_DWORD *)(v4 + 124) != 3 )
    {
      v5 = *(_WORD *)(a1 + 166);
      if ( (v5 & 0xFFFD) != 0 )
      {
        if ( v5 == 4 )
          OPRawPortWrite(a1, "\x1B%-12345X", 9u);
      }
      else if ( *(char *)(a1 + 132) < 0 )
      {
        OPRawPortWrite(a1, gstrCtlD, 1u);
      }
    }
    if ( (*(_BYTE *)(*(_QWORD *)(a1 + 2136) + 100LL) & 1) != 0 )
    {
      v6 = *(_QWORD *)(a1 + 2144);
      if ( *(_DWORD *)(v6 + 168) )
      {
        OPSendInvocation(a1, (unsigned int *)(v6 + 168));
      }
      else if ( (*(_BYTE *)(v6 + 4) & 0x10) == 0 )
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
0x180015180  mov     [rsp+arg_0], rbx
0x180015185  push    r14
0x180015187  sub     rsp, 20h
0x18001518b  mov     edx, 12h
0x180015190  mov     rbx, rcx
0x180015193  call    DSCSend
0x180015198  mov     edx, 0Ah
0x18001519d  mov     rcx, rbx
0x1800151a0  call    DSCSend
0x1800151a5  mov     edx, 9
0x1800151aa  mov     rcx, rbx
0x1800151ad  call    BSendBoundingBox
0x1800151b2  mov     edx, 5
0x1800151b7  mov     rcx, rbx
0x1800151ba  call    DSCSend
0x1800151bf  mov     edx, 6
0x1800151c4  mov     rcx, rbx
0x1800151c7  call    DSCSend
0x1800151cc  mov     rcx, [rbx+60h]
0x1800151d0  mov     r14d, 4
0x1800151d6  mov     eax, [rcx+88h]
0x1800151dc  dec     eax
0x1800151de  cmp     eax, r14d
0x1800151e1  ja      short loc_180015225
0x1800151e3  cmp     dword ptr [rcx+7Ch], 2
0x1800151e7  jz      short loc_180015225
0x1800151e9  cmp     dword ptr [rbx+868h], 0
0x1800151f0  jge     short loc_1800151FB
0x1800151f2  cmp     dword ptr [rbx+0E54h], 0
0x1800151f9  jz      short loc_180015225
0x1800151fb  mov     r8d, 0Ah
0x180015201  lea     rdx, PSFRAG_finalpageNup; "finalpage "
0x180015208  mov     rcx, rbx
0x18001520b  call    OPRawPortWrite
0x180015210  mov     r8d, 2
0x180015216  lea     rdx, gstrCRLF; "\r\n"
0x18001521d  mov     rcx, rbx
0x180015220  call    OPRawPortWrite
0x180015225  mov     eax, [rbx+868h]
0x18001522b  test    eax, eax
0x18001522d  jns     short loc_180015269
0x18001522f  bt      eax, 1Dh
0x180015233  jnb     short loc_180015252
0x180015235  mov     r8d, 2Ch ; ','
0x18001523b  lea     rdx, PSFRAG_termfulldictMH; "Pscript_WinNT_Full dup /terminate get e"...
0x180015242  mov     rcx, rbx
0x180015245  call    OPRawPortWrite
0x18001524a  btr     dword ptr [rbx+868h], 1Dh
0x180015252  mov     r8d, 2Fh ; '/'
0x180015258  lea     rdx, PSFRAG_termminhdrdict; "Pscript_WinNT_Min dup /min_terminate ge"...
0x18001525f  mov     rcx, rbx
0x180015262  call    OPRawPortWrite
0x180015267  jmp     short loc_1800152DE
0x180015269  mov     rax, [rbx+60h]
0x18001526d  mov     rcx, rbx
0x180015270  test    dword ptr [rax+7Ch], 0FFFFFFFDh
0x180015277  jz      short loc_1800152B2
0x180015279  mov     r8d, 43h ; 'C'
0x18001527f  lea     rdx, PSFRAG_termfulldict; "/Pscript_WinNT_Full /ProcSet findresour"...
0x180015286  call    OPRawPortWrite
0x18001528b  test    byte ptr [rbx+868h], 2
0x180015292  jz      short loc_1800152D6
0x180015294  mov     r8d, 2Eh ; '.'
0x18001529a  lea     rdx, PSFRAG_termcompatdict; "Pscript_WinNT_Compat dup /terminate get"...
0x1800152a1  mov     rcx, rbx
0x1800152a4  call    OPRawPortWrite
0x1800152a9  and     dword ptr [rbx+868h], 0FFFFFFFDh
0x1800152b0  jmp     short loc_1800152D6
0x1800152b2  mov     r8d, 2Ch ; ','
0x1800152b8  lea     rdx, PSFRAG_termincrdict; "Pscript_WinNT_Incr dup /terminate get e"...
0x1800152bf  call    OPRawPortWrite
0x1800152c4  mov     rax, [rbx+60h]
0x1800152c8  cmp     dword ptr [rax+7Ch], 0
0x1800152cc  jnz     short loc_1800152D6
0x1800152ce  mov     rcx, rbx
0x1800152d1  call    VMRestoreLevel1
0x1800152d6  mov     rcx, rbx
0x1800152d9  call    GSSendRestoreForErrHandler
0x1800152de  mov     rax, [rbx+60h]
0x1800152e2  cmp     dword ptr [rax+7Ch], 2
0x1800152e6  jz      short loc_18001531B
0x1800152e8  cmp     dword ptr [rbx+868h], 0
0x1800152ef  jl      short loc_18001531B
0x1800152f1  cmp     dword ptr [rbx+874h], 0
0x1800152f8  jnz     short loc_18001530C
0x1800152fa  mov     r8d, [rbx+87Ch]
0x180015301  mov     rdx, r14
0x180015304  mov     rcx, rbx
0x180015307  call    DSCSend
0x18001530c  lea     rdx, DSC_LastPage; "(%%%%[LastPage]%%%%) = \r\n"
0x180015313  mov     rcx, rbx
0x180015316  call    DSCSend
0x18001531b  mov     edx, 13h
0x180015320  mov     rcx, rbx
0x180015323  call    DSCSend
0x180015328  mov     rax, [rbx+60h]
0x18001532c  cmp     dword ptr [rax+7Ch], 2
0x180015330  jz      loc_1800153C5
0x180015336  cmp     dword ptr [rax+7Ch], 3
0x18001533a  jz      short loc_180015380
0x18001533c  movzx   eax, word ptr [rbx+0A6h]
0x180015343  mov     ecx, 0FFFDh
0x180015348  test    cx, ax
0x18001534b  jz      short loc_180015362
0x18001534d  cmp     ax, r14w
0x180015351  jnz     short loc_180015380
0x180015353  mov     r8d, 9
0x180015359  lea     rdx, gstrTbcpEnd; "\x1B%-12345X"
0x180015360  jmp     short loc_180015378
0x180015362  test    byte ptr [rbx+84h], 80h
0x180015369  jz      short loc_180015380
0x18001536b  mov     r8d, 1
0x180015371  lea     rdx, gstrCtlD
0x180015378  mov     rcx, rbx
0x18001537b  call    OPRawPortWrite
0x180015380  mov     rax, [rbx+858h]
0x180015387  test    byte ptr [rax+64h], 1
0x18001538b  jz      short loc_1800153C5
0x18001538d  mov     rax, [rbx+860h]
0x180015394  lea     rdx, [rax+0A8h]
0x18001539b  cmp     dword ptr [rdx], 0
0x18001539e  jz      short loc_1800153AA
0x1800153a0  mov     rcx, rbx
0x1800153a3  call    OPSendInvocation
0x1800153a8  jmp     short loc_1800153C5
0x1800153aa  test    byte ptr [rax+4], 10h
0x1800153ae  jnz     short loc_1800153C5
0x1800153b0  mov     r8d, 1Ch
0x1800153b6  lea     rdx, PSFRAG_JCLEnd; "\x1B%-12345X@PJL EOJ\n\x1B%-12345X\n"
0x1800153bd  mov     rcx, rbx
0x1800153c0  call    OPRawPortWrite
0x1800153c5  mov     edx, 14h
0x1800153ca  mov     rcx, rbx
0x1800153cd  call    DSCSend
0x1800153d2  xor     eax, eax
0x1800153d4  cmp     [rbx+0D70h], eax
0x1800153da  mov     rbx, [rsp+28h+arg_0]
0x1800153df  setz    al
0x1800153e2  add     rsp, 20h
0x1800153e6  pop     r14
0x1800153e8  retn
```
