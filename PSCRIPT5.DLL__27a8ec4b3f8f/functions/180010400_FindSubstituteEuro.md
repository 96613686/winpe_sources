# FindSubstituteEuro

- ea: `0x180010400`
- end: `0x180010716`
- name: `FindSubstituteEuro`
- size: `790`
- prototype: `__int64 __fastcall(__int64, char, __int16, __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ec74`

## callees

- `0x180001f20`
- `0x18000f960`
- `0x180010400`

## string_xrefs

- `0x180010445`: `Courier`
- `0x180010477`: `Courier-Oblique`
- `0x1800104af`: `Courier-Bold`
- `0x1800104e1`: `Courier-BoldOblique`

## pseudocode

```c
__int64 __fastcall FindSubstituteEuro(__int64 a1, char a2, __int16 a3, __int16 a4)
{
  __int64 v4; // rdx
  bool v5; // zf
  __int64 v6; // rax
  char *v7; // r8
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  __int64 v12; // rax
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  __int64 v17; // rax
  const char *v18; // r9
  const char *v19; // r9
  const char *v20; // r9
  const char *v21; // r9
  char *v22; // rax
  char v24[64]; // [rsp+20h] [rbp-50h] BYREF

  if ( (a2 & 1) != 0 )
  {
    v4 = 60;
    v5 = a3 == 0;
    v6 = 2147483646;
    v7 = v24;
    if ( v5 )
    {
      if ( a4 )
      {
        v9 = "Courier-Oblique";
        do
        {
          if ( !v6 )
            break;
          if ( !*v9 )
            break;
          *v7++ = *v9++;
          --v6;
          --v4;
        }
        while ( v4 );
      }
      else
      {
        v8 = "Courier";
        do
        {
          if ( !v6 )
            break;
          if ( !*v8 )
            break;
          *v7++ = *v8++;
          --v6;
          --v4;
        }
        while ( v4 );
      }
    }
    else if ( a4 )
    {
      v11 = "Courier-BoldOblique";
      do
      {
        if ( !v6 )
          break;
        if ( !*v11 )
          break;
        *v7++ = *v11++;
        --v6;
        --v4;
      }
      while ( v4 );
    }
    else
    {
      v10 = "Courier-Bold";
      do
      {
        if ( !v6 )
          break;
        if ( !*v10 )
          break;
        *v7++ = *v10++;
        --v6;
        --v4;
      }
      while ( v4 );
    }
  }
  else if ( (a2 & 0x10) != 0 )
  {
    v12 = 2147483646;
    v5 = a3 == 0;
    v7 = v24;
    v4 = 60;
    if ( v5 )
    {
      if ( a4 )
      {
        v14 = "Times-Italic";
        do
        {
          if ( !v12 )
            break;
          if ( !*v14 )
            break;
          *v7++ = *v14++;
          --v12;
          --v4;
        }
        while ( v4 );
      }
      else
      {
        v13 = "Times-Roman";
        do
        {
          if ( !v12 )
            break;
          if ( !*v13 )
            break;
          *v7++ = *v13++;
          --v12;
          --v4;
        }
        while ( v4 );
      }
    }
    else if ( a4 )
    {
      v16 = "Times-BoldItalic";
      do
      {
        if ( !v12 )
          break;
        if ( !*v16 )
          break;
        *v7++ = *v16++;
        --v12;
        --v4;
      }
      while ( v4 );
    }
    else
    {
      v15 = "Times-Bold";
      do
      {
        if ( !v12 )
          break;
        if ( !*v15 )
          break;
        *v7++ = *v15++;
        --v12;
        --v4;
      }
      while ( v4 );
    }
  }
  else
  {
    if ( (a2 & 0x20) == 0 )
      return 0xFFFFFFFFLL;
    v17 = 2147483646;
    v5 = a3 == 0;
    v7 = v24;
    v4 = 60;
    if ( v5 )
    {
      if ( a4 )
      {
        v19 = "Helvetica-Oblique";
        do
        {
          if ( !v17 )
            break;
          if ( !*v19 )
            break;
          *v7++ = *v19++;
          --v17;
          --v4;
        }
        while ( v4 );
      }
      else
      {
        v18 = "Helvetica";
        do
        {
          if ( !v17 )
            break;
          if ( !*v18 )
            break;
          *v7++ = *v18++;
          --v17;
          --v4;
        }
        while ( v4 );
      }
    }
    else if ( a4 )
    {
      v21 = "Helvetica-BoldOblique";
      do
      {
        if ( !v17 )
          break;
        if ( !*v21 )
          break;
        *v7++ = *v21++;
        --v17;
        --v4;
      }
      while ( v4 );
    }
    else
    {
      v20 = "Helvetica-Bold";
      do
      {
        if ( !v17 )
          break;
        if ( !*v20 )
          break;
        *v7++ = *v20++;
        --v17;
        --v4;
      }
      while ( v4 );
    }
  }
  v22 = v7 - 1;
  if ( v4 )
    v22 = v7;
  *v22 = 0;
  return BSearchNameIndex(*(_QWORD *)(a1 + 3712), v24, (__int64)v7, *(_DWORD *)(a1 + 3720) - 1);
}

```

## disassembly

```asm
0x180010400  mov     [rsp-8+arg_8], rbx
0x180010405  push    rbp
0x180010406  mov     rbp, rsp
0x180010409  sub     rsp, 70h
0x18001040d  mov     rax, cs:__security_cookie
0x180010414  xor     rax, rsp
0x180010417  mov     [rbp+var_10], rax
0x18001041b  mov     ebx, 1
0x180010420  mov     r11, rcx
0x180010423  test    bl, dl
0x180010425  jz      loc_180010513
0x18001042b  xor     ecx, ecx
0x18001042d  lea     edx, [rbx+3Bh]
0x180010430  test    r8w, r8w
0x180010434  mov     eax, 7FFFFFFEh
0x180010439  lea     r8, [rbp+var_50]
0x18001043d  jnz     short loc_1800104A9
0x18001043f  test    r9w, r9w
0x180010443  jnz     short loc_180010477
0x180010445  lea     r9, aCourier_0; "Courier"
0x18001044c  test    rax, rax
0x18001044f  jz      loc_1800106CF
0x180010455  mov     r10b, [r9]
0x180010458  test    r10b, r10b
0x18001045b  jz      loc_1800106CF
0x180010461  mov     [r8], r10b
0x180010464  add     r9, rbx
0x180010467  add     r8, rbx
0x18001046a  sub     rax, rbx
0x18001046d  sub     rdx, rbx
0x180010470  jnz     short loc_18001044C
0x180010472  jmp     loc_1800106CF
0x180010477  lea     r9, aCourierOblique; "Courier-Oblique"
0x18001047e  test    rax, rax
0x180010481  jz      loc_1800106CF
0x180010487  mov     r10b, [r9]
0x18001048a  test    r10b, r10b
0x18001048d  jz      loc_1800106CF
0x180010493  mov     [r8], r10b
0x180010496  add     r9, rbx
0x180010499  add     r8, rbx
0x18001049c  sub     rax, rbx
0x18001049f  sub     rdx, rbx
0x1800104a2  jnz     short loc_18001047E
0x1800104a4  jmp     loc_1800106CF
0x1800104a9  test    r9w, r9w
0x1800104ad  jnz     short loc_1800104E1
0x1800104af  lea     r9, aCourierBold; "Courier-Bold"
0x1800104b6  test    rax, rax
0x1800104b9  jz      loc_1800106CF
0x1800104bf  mov     r10b, [r9]
0x1800104c2  test    r10b, r10b
0x1800104c5  jz      loc_1800106CF
0x1800104cb  mov     [r8], r10b
0x1800104ce  add     r9, rbx
0x1800104d1  add     r8, rbx
0x1800104d4  sub     rax, rbx
0x1800104d7  sub     rdx, rbx
0x1800104da  jnz     short loc_1800104B6
0x1800104dc  jmp     loc_1800106CF
0x1800104e1  lea     r9, aCourierBoldobl; "Courier-BoldOblique"
0x1800104e8  test    rax, rax
0x1800104eb  jz      loc_1800106CF
0x1800104f1  mov     r10b, [r9]
0x1800104f4  test    r10b, r10b
0x1800104f7  jz      loc_1800106CF
0x1800104fd  mov     [r8], r10b
0x180010500  add     r9, rbx
0x180010503  add     r8, rbx
0x180010506  sub     rax, rbx
0x180010509  sub     rdx, rbx
0x18001050c  jnz     short loc_1800104E8
0x18001050e  jmp     loc_1800106CF
0x180010513  test    dl, 10h
0x180010516  jz      loc_180010604
0x18001051c  xor     ecx, ecx
0x18001051e  mov     eax, 7FFFFFFEh
0x180010523  test    r8w, r8w
0x180010527  lea     r8, [rbp+var_50]
0x18001052b  lea     edx, [rcx+3Ch]
0x18001052e  jnz     short loc_18001059A
0x180010530  test    r9w, r9w
0x180010534  jnz     short loc_180010568
0x180010536  lea     r9, aTimesRoman; "Times-Roman"
0x18001053d  test    rax, rax
0x180010540  jz      loc_1800106CF
0x180010546  mov     r10b, [r9]
0x180010549  test    r10b, r10b
0x18001054c  jz      loc_1800106CF
0x180010552  mov     [r8], r10b
0x180010555  add     r9, rbx
0x180010558  add     r8, rbx
0x18001055b  sub     rax, rbx
0x18001055e  sub     rdx, rbx
0x180010561  jnz     short loc_18001053D
0x180010563  jmp     loc_1800106CF
0x180010568  lea     r9, aTimesItalic; "Times-Italic"
0x18001056f  test    rax, rax
0x180010572  jz      loc_1800106CF
0x180010578  mov     r10b, [r9]
0x18001057b  test    r10b, r10b
0x18001057e  jz      loc_1800106CF
0x180010584  mov     [r8], r10b
0x180010587  add     r9, rbx
0x18001058a  add     r8, rbx
0x18001058d  sub     rax, rbx
0x180010590  sub     rdx, rbx
0x180010593  jnz     short loc_18001056F
0x180010595  jmp     loc_1800106CF
0x18001059a  test    r9w, r9w
0x18001059e  jnz     short loc_1800105D2
0x1800105a0  lea     r9, aTimesBold; "Times-Bold"
0x1800105a7  test    rax, rax
0x1800105aa  jz      loc_1800106CF
0x1800105b0  mov     r10b, [r9]
0x1800105b3  test    r10b, r10b
0x1800105b6  jz      loc_1800106CF
0x1800105bc  mov     [r8], r10b
0x1800105bf  add     r9, rbx
0x1800105c2  add     r8, rbx
0x1800105c5  sub     rax, rbx
0x1800105c8  sub     rdx, rbx
0x1800105cb  jnz     short loc_1800105A7
0x1800105cd  jmp     loc_1800106CF
0x1800105d2  lea     r9, aTimesBolditali; "Times-BoldItalic"
0x1800105d9  test    rax, rax
0x1800105dc  jz      loc_1800106CF
0x1800105e2  mov     r10b, [r9]
0x1800105e5  test    r10b, r10b
0x1800105e8  jz      loc_1800106CF
0x1800105ee  mov     [r8], r10b
0x1800105f1  add     r9, rbx
0x1800105f4  add     r8, rbx
0x1800105f7  sub     rax, rbx
0x1800105fa  sub     rdx, rbx
0x1800105fd  jnz     short loc_1800105D9
0x1800105ff  jmp     loc_1800106CF
0x180010604  test    dl, 20h
0x180010607  jz      loc_1800106F8
0x18001060d  xor     ecx, ecx
0x18001060f  mov     eax, 7FFFFFFEh
0x180010614  test    r8w, r8w
0x180010618  lea     r8, [rbp+var_50]
0x18001061c  lea     edx, [rcx+3Ch]
0x18001061f  jnz     short loc_18001067D
0x180010621  test    r9w, r9w
0x180010625  jnz     short loc_180010656
0x180010627  lea     r9, aHelvetica; "Helvetica"
0x18001062e  test    rax, rax
0x180010631  jz      loc_1800106CF
0x180010637  mov     r10b, [r9]
0x18001063a  test    r10b, r10b
0x18001063d  jz      loc_1800106CF
0x180010643  mov     [r8], r10b
0x180010646  add     r9, rbx
0x180010649  add     r8, rbx
0x18001064c  sub     rax, rbx
0x18001064f  sub     rdx, rbx
0x180010652  jnz     short loc_18001062E
0x180010654  jmp     short loc_1800106CF
0x180010656  lea     r9, aHelveticaObliq; "Helvetica-Oblique"
0x18001065d  test    rax, rax
0x180010660  jz      short loc_1800106CF
0x180010662  mov     r10b, [r9]
0x180010665  test    r10b, r10b
0x180010668  jz      short loc_1800106CF
0x18001066a  mov     [r8], r10b
0x18001066d  add     r9, rbx
0x180010670  add     r8, rbx
0x180010673  sub     rax, rbx
0x180010676  sub     rdx, rbx
0x180010679  jnz     short loc_18001065D
0x18001067b  jmp     short loc_1800106CF
0x18001067d  test    r9w, r9w
0x180010681  jnz     short loc_1800106AA
0x180010683  lea     r9, aHelveticaBold; "Helvetica-Bold"
0x18001068a  test    rax, rax
0x18001068d  jz      short loc_1800106CF
0x18001068f  mov     r10b, [r9]
0x180010692  test    r10b, r10b
0x180010695  jz      short loc_1800106CF
0x180010697  mov     [r8], r10b
0x18001069a  add     r9, rbx
0x18001069d  add     r8, rbx
0x1800106a0  sub     rax, rbx
0x1800106a3  sub     rdx, rbx
0x1800106a6  jnz     short loc_18001068A
0x1800106a8  jmp     short loc_1800106CF
0x1800106aa  lea     r9, aHelveticaBoldo; "Helvetica-BoldOblique"
0x1800106b1  test    rax, rax
0x1800106b4  jz      short loc_1800106CF
0x1800106b6  mov     r10b, [r9]
0x1800106b9  test    r10b, r10b
0x1800106bc  jz      short loc_1800106CF
0x1800106be  mov     [r8], r10b
0x1800106c1  add     r9, rbx
0x1800106c4  add     r8, rbx
0x1800106c7  sub     rax, rbx
0x1800106ca  sub     rdx, rbx
0x1800106cd  jnz     short loc_1800106B1
0x1800106cf  test    rdx, rdx
0x1800106d2  lea     rax, [r8-1]
0x1800106d6  lea     rdx, [rbp+var_50]
0x1800106da  cmovnz  rax, r8
0x1800106de  mov     [rax], cl
0x1800106e0  mov     r9d, [r11+0E88h]
0x1800106e7  mov     rcx, [r11+0E80h]
0x1800106ee  sub     r9d, ebx
0x1800106f1  call    BSearchNameIndex
0x1800106f6  jmp     short loc_1800106FB
0x1800106f8  or      eax, 0FFFFFFFFh
0x1800106fb  mov     rcx, [rbp+var_10]
0x1800106ff  xor     rcx, rsp; StackCookie
0x180010702  call    __security_check_cookie
0x180010707  mov     rbx, [rsp+70h+arg_8]
0x18001070f  add     rsp, 70h
0x180010713  pop     rbp
0x180010714  retn
```
