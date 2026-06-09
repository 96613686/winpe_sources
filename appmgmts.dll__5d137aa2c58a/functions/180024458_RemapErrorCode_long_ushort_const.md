# RemapErrorCode(long,ushort const *)

- ea: `0x180024458`
- end: `0x1800245e9`
- name: `?RemapErrorCode@@YAJJPEBG@Z`
- size: `401`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bcc0`
- `0x18001c258`
- `0x18001cb90`
- `0x18001d240`
- `0x18001e8ac`
- `0x18001eec0`
- `0x18001f0b0`
- `0x18001f570`
- `0x18001f800`
- `0x18001fa10`
- `0x180020180`
- `0x1800208c4`
- `0x180021b70`
- `0x180021dd0`
- `0x180022610`
- `0x1800226f0`
- `0x180022940`
- `0x180022e00`
- `0x180023050`
- `0x180023330`
- `0x18002371c`
- `0x180028190`
- `0x1800283e0`
- `0x180028730`

## callees

- `0x18001b1a0`
- `0x180024458`

## pseudocode

```c
__int64 __fastcall RemapErrorCode(int a1, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  int v4; // edx

  if ( a1 >= 0 )
    return 0;
  if ( a1 > -2147016689 )
  {
    if ( a1 > -2147016651 )
    {
      if ( a1 == -2147016646 || a1 != -2147016639 && a1 != -2147016426 )
        goto LABEL_15;
    }
    else
    {
      if ( a1 == -2147016651 || a1 == -2147016670 )
        goto LABEL_15;
      if ( a1 == -2147016668 )
      {
        v3 = -2147221139;
        goto LABEL_16;
      }
      if ( (unsigned int)(a1 + 2147016665) <= 6 )
      {
        v4 = 75;
        if ( _bittest(&v4, a1 + 2147016665) )
          goto LABEL_33;
      }
      if ( a1 == -2147016657 )
      {
LABEL_37:
        v3 = -2147221138;
        goto LABEL_16;
      }
      if ( a1 != -2147016656 )
        goto LABEL_15;
    }
    v3 = -2147221143;
    goto LABEL_16;
  }
  if ( a1 == -2147016689 )
  {
LABEL_15:
    v3 = a1;
    goto LABEL_16;
  }
  if ( a1 > -2147024713 )
  {
    if ( a1 == -2147023671 || a1 == -2147023541 || a1 == -2147023436 )
      goto LABEL_15;
    if ( a1 != -2147019886 )
    {
      if ( a1 == -2147016694 )
        goto LABEL_37;
      if ( a1 != -2147016693 )
        goto LABEL_15;
LABEL_25:
      v3 = -2147221141;
      goto LABEL_16;
    }
LABEL_26:
    v3 = -2147221142;
    goto LABEL_16;
  }
  switch ( a1 )
  {
    case -2147024713:
      goto LABEL_26;
    case -2147463168:
      goto LABEL_25;
    case -2147463156:
      goto LABEL_37;
    case -2147463154:
      goto LABEL_26;
    case -2147463153:
      goto LABEL_37;
    case -2147024891:
      goto LABEL_33;
  }
  v3 = -2147024882;
  if ( a1 != -2147024888 && a1 != -2147024882 )
  {
    if ( a1 != -2147024810 )
      goto LABEL_15;
LABEL_33:
    v3 = -2147024891;
  }
LABEL_16:
  if ( gDebug )
    _DebugMsg(2, 0xCA3u, (unsigned int)a1, v3);
  return v3;
}

```

## disassembly

```asm
0x180024458  push    rbx
0x18002445a  sub     rsp, 20h
0x18002445e  test    ecx, ecx
0x180024460  js      short loc_180024469
0x180024462  xor     eax, eax
0x180024464  jmp     loc_180024508
0x180024469  mov     eax, 8007200Fh
0x18002446e  mov     r8d, 80070005h
0x180024474  cmp     ecx, eax
0x180024476  jg      loc_18002454C
0x18002447c  jz      short loc_1800244E6
0x18002447e  mov     eax, 800700B7h
0x180024483  cmp     ecx, eax
0x180024485  jg      loc_18002450E
0x18002448b  jz      loc_180024545
0x180024491  cmp     ecx, 80005000h
0x180024497  jz      loc_18002453E
0x18002449d  cmp     ecx, 8000500Ch
0x1800244a3  jz      loc_1800245A2
0x1800244a9  cmp     ecx, 8000500Eh
0x1800244af  jz      loc_180024545
0x1800244b5  cmp     ecx, 8000500Fh
0x1800244bb  jz      loc_1800245A2
0x1800244c1  cmp     ecx, r8d
0x1800244c4  jz      loc_18002457C
0x1800244ca  lea     ebx, [r8+9]
0x1800244ce  cmp     ecx, 80070008h
0x1800244d4  jz      short loc_1800244E8
0x1800244d6  cmp     ecx, ebx
0x1800244d8  jz      short loc_1800244E8
0x1800244da  cmp     ecx, 80070056h
0x1800244e0  jz      loc_18002457C
0x1800244e6  mov     ebx, ecx
0x1800244e8  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x1800244ef  jz      short loc_180024506
0x1800244f1  mov     r8d, ecx
0x1800244f4  mov     r9d, ebx
0x1800244f7  mov     ecx, 2; unsigned int
0x1800244fc  mov     edx, 0CA3h; unsigned int
0x180024501  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180024506  mov     eax, ebx
0x180024508  add     rsp, 20h
0x18002450c  pop     rbx
0x18002450d  retn
0x18002450e  cmp     ecx, 800704C9h
0x180024514  jz      short loc_1800244E6
0x180024516  cmp     ecx, 8007054Bh
0x18002451c  jz      short loc_1800244E6
0x18002451e  cmp     ecx, 800705B4h
0x180024524  jz      short loc_1800244E6
0x180024526  cmp     ecx, 80071392h
0x18002452c  jz      short loc_180024545
0x18002452e  cmp     ecx, 8007200Ah
0x180024534  jz      short loc_1800245A2
0x180024536  cmp     ecx, 8007200Bh
0x18002453c  jnz     short loc_1800244E6
0x18002453e  mov     ebx, 8004016Bh
0x180024543  jmp     short loc_1800244E8
0x180024545  mov     ebx, 8004016Ah
0x18002454a  jmp     short loc_1800244E8
0x18002454c  mov     eax, 80072035h
0x180024551  cmp     ecx, eax
0x180024553  jg      short loc_1800245B6
0x180024555  jz      short loc_1800244E6
0x180024557  cmp     ecx, 80072022h
0x18002455d  jz      short loc_1800244E6
0x18002455f  cmp     ecx, 80072024h
0x180024565  jz      short loc_1800245AC
0x180024567  lea     eax, [rcx+7FF8DFD9h]
0x18002456d  cmp     eax, 6
0x180024570  ja      short loc_180024584
0x180024572  mov     edx, 4Bh ; 'K'
0x180024577  bt      edx, eax
0x18002457a  jnb     short loc_180024584
0x18002457c  mov     ebx, r8d
0x18002457f  jmp     loc_1800244E8
0x180024584  cmp     ecx, 8007202Fh
0x18002458a  jz      short loc_1800245A2
0x18002458c  cmp     ecx, 80072030h
0x180024592  jnz     loc_1800244E6
0x180024598  mov     ebx, 80040169h
0x18002459d  jmp     loc_1800244E8
0x1800245a2  mov     ebx, 8004016Eh
0x1800245a7  jmp     loc_1800244E8
0x1800245ac  mov     ebx, 8004016Dh
0x1800245b1  jmp     loc_1800244E8
0x1800245b6  cmp     ecx, 8007203Ah
0x1800245bc  jz      loc_1800244E6
0x1800245c2  cmp     ecx, 80072041h
0x1800245c8  jz      short loc_180024598
0x1800245ca  cmp     ecx, 80072115h
0x1800245d0  jz      loc_1800244E6
0x1800245d6  cmp     ecx, 80072116h
0x1800245dc  jz      short loc_180024598
0x1800245de  lea     eax, [rcx+7FF8DEE9h]
0x1800245e4  jmp     loc_1800244E6
```
