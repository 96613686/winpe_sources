# IsRestoreNeeded(ushort const *,ushort const *,ushort const *,int *,ushort * *)

- ea: `0x1800202f8`
- end: `0x1800206be`
- name: `?IsRestoreNeeded@@YAJPEBG00PEAHPEAPEAG@Z`
- size: `966`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017fe8`

## callees

- `0x1800063b0`
- `0x1800202f8`
- `0x1800206c4`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800846c0`
- `0x180085dec`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800205f1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800205f1`

## string_xrefs

- `0x1800205d7`: `ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get value failed`
- `0x1800204b6`: `ReadRegKeyValue32W(pwszRestoreKey) to get value failed`
- `0x180020518`: `IsRestoreNeeded, ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get size failed`
- `0x1800204a5`: `IsRestoreNeeded, ReadRegKeyValue32W(pwszRestoreKey) to get value failed`
- `0x180020529`: `ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get size failed`
- `0x1800203ec`: `ReadRegKeyValue32W(pwszRestoreKey) to get size failed`
- `0x1800205c6`: `IsRestoreNeeded, ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get value failed`
- `0x1800203db`: `IsRestoreNeeded, ReadRegKeyValue32W(pwszRestoreKey) to get size failed`
- `0x18002033b`: `com\complus\dtc\shared\util\vssbackup.cpp`
- `0x18002037e`: `IsRestoreNeeded (com\complus\dtc\shared\util\vssbackup.cpp@46): IsRestoreNeeded, pbRestoreNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsRestoreNeeded(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4,
        unsigned __int16 **a5)
{
  HKEY v6; // rcx
  const unsigned __int16 *v7; // r8
  unsigned __int8 *v8; // r14
  int v9; // eax
  signed int v10; // ebx
  unsigned __int8 *v11; // rbp
  BOOL v12; // edi
  const wchar_t *v13; // rax
  __int64 v14; // r9
  HKEY v15; // rcx
  const unsigned __int16 *v16; // r8
  int v17; // eax
  HKEY v18; // rcx
  const unsigned __int16 *v19; // r8
  int v20; // eax
  HKEY v21; // rcx
  const unsigned __int16 *v22; // r8
  int v23; // eax
  unsigned __int16 **v24; // rsi
  __int64 v26; // [rsp+28h] [rbp-50h]
  const wchar_t *v27; // [rsp+30h] [rbp-48h]
  __int64 v28; // [rsp+38h] [rbp-40h]
  unsigned int Size; // [rsp+90h] [rbp+18h] BYREF
  int Size_4; // [rsp+94h] [rbp+1Ch]

  Size_4 = HIDWORD(a3);
  Size = 0;
  TraceStringInline(
    17,
    6,
    L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
    43,
    L"IsRestoreNeeded",
    0,
    L"In, pwszRestoreKey = %ws, pwszMsdtcRestoreKey = %ws, pwszRestoreValue = %ws",
    L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\RestoreSession",
    L"SYSTEM\\CurrentControlSet\\Control\\MSDTC\\ASR\\RestoreSession",
    L"LastInstance");
  if ( !a4 )
    DtcInternalErrorW(L"IsRestoreNeeded (com\\complus\\dtc\\shared\\util\\vssbackup.cpp@46): IsRestoreNeeded, pbRestoreNeeded");
  v8 = 0;
  *a4 = 0;
  v9 = ReadRegKeyValue32W(v6, L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\RestoreSession", v7, 0, &Size);
  v10 = v9;
  if ( v9 )
  {
    v11 = 0;
    if ( v9 == 2 )
    {
LABEL_5:
      v10 = 0;
      v12 = 0;
      goto LABEL_34;
    }
    if ( v9 != 234 )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      TraceFileW(
        v10,
        L"IsRestoreNeeded, ReadRegKeyValue32W(pwszRestoreKey) to get size failed",
        L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
        0x44u);
      v13 = L"ReadRegKeyValue32W(pwszRestoreKey) to get size failed";
      v14 = 69;
LABEL_10:
      v27 = v13;
      LODWORD(v26) = v10;
LABEL_11:
      TraceStringInline(17, 1, L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp", v14, L"IsRestoreNeeded", v26, v27);
      v12 = 0;
      goto LABEL_34;
    }
  }
  v11 = (unsigned __int8 *)operator new(Size);
  if ( !v11 )
  {
    v10 = -2147024882;
    TraceFileW(
      -2147024882,
      L"IsRestoreNeeded, new BYTE[cbSizeOfData] failed",
      L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
      0x4Eu);
    v27 = L"new BYTE[cbSizeOfData] failed";
    v14 = 79;
    LODWORD(v26) = -2147024882;
    goto LABEL_11;
  }
  v17 = ReadRegKeyValue32W(
          v15,
          L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\RestoreSession",
          v16,
          v11,
          &Size);
  v10 = v17;
  if ( v17 )
  {
    if ( v17 == 2 )
      goto LABEL_5;
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    TraceFileW(
      v10,
      L"IsRestoreNeeded, ReadRegKeyValue32W(pwszRestoreKey) to get value failed",
      L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
      0x61u);
    v13 = L"ReadRegKeyValue32W(pwszRestoreKey) to get value failed";
    v14 = 98;
    goto LABEL_10;
  }
  Size = 0;
  v20 = ReadRegKeyValue32W(v18, L"SYSTEM\\CurrentControlSet\\Control\\MSDTC\\ASR\\RestoreSession", v19, 0, &Size);
  v10 = v20;
  if ( v20 )
  {
    if ( v20 == 2 )
    {
LABEL_21:
      v10 = 0;
      v12 = 1;
      goto LABEL_34;
    }
    if ( v20 != 234 )
    {
      if ( v20 > 0 )
        v10 = (unsigned __int16)v20 | 0x80070000;
      TraceFileW(
        v10,
        L"IsRestoreNeeded, ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get size failed",
        L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
        0x79u);
      v13 = L"ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get size failed";
      v14 = 122;
      goto LABEL_10;
    }
  }
  v8 = (unsigned __int8 *)operator new(Size);
  if ( !v8 )
  {
    v10 = -2147024882;
    TraceFileW(
      -2147024882,
      L"IsRestoreNeeded, new BYTE[cbSizeOfData] failed",
      L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
      0x83u);
    v14 = 132;
    v27 = L"new BYTE[cbSizeOfData] failed";
    LODWORD(v26) = -2147024882;
    goto LABEL_11;
  }
  v23 = ReadRegKeyValue32W(v21, L"SYSTEM\\CurrentControlSet\\Control\\MSDTC\\ASR\\RestoreSession", v22, v8, &Size);
  v10 = v23;
  if ( v23 )
  {
    if ( v23 != 2 )
    {
      if ( v23 > 0 )
        v10 = (unsigned __int16)v23 | 0x80070000;
      TraceFileW(
        v10,
        L"IsRestoreNeeded, ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get value failed",
        L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
        0x96u);
      v13 = L"ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get value failed";
      v14 = 151;
      goto LABEL_10;
    }
    goto LABEL_21;
  }
  v10 = 0;
  v12 = lstrcmpiW((LPCWSTR)v11, (LPCWSTR)v8) != 0;
LABEL_34:
  *a4 = v12;
  v24 = a5;
  if ( a5 )
    *a5 = (unsigned __int16 *)v11;
  if ( v10 < 0 || !v24 )
    operator delete(v11);
  operator delete(v8);
  if ( v24 && *v24 )
  {
    LODWORD(v28) = v12;
    LODWORD(v26) = v10;
    TraceStringInline(
      17,
      6,
      L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
      179,
      L"IsRestoreNeeded",
      v26,
      L"Out, bRestoreNeeded = %d, InstanceValue = %ws",
      v28,
      *v24);
  }
  else
  {
    LODWORD(v28) = v12;
    LODWORD(v26) = v10;
    TraceStringInline(
      17,
      6,
      L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
      183,
      L"IsRestoreNeeded",
      v26,
      L"Out, bRestoreNeeded = %d",
      v28);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800202f8  mov     r11, rsp
0x1800202fb  mov     [r11+8], rbx
0x1800202ff  mov     [r11+10h], rbp
0x180020303  mov     [r11+18h], r8
0x180020307  push    rsi
0x180020308  push    rdi
0x180020309  push    r12
0x18002030b  push    r13
0x18002030d  push    r14
0x18002030f  sub     rsp, 50h
0x180020313  lea     rax, aLastinstance; "LastInstance"
0x18002031a  mov     dword ptr [r11+18h], 0
0x180020322  mov     [r11-30h], rax
0x180020326  lea     r13, aSoftwareMicros_5; "SOFTWARE\\MICROSOFT\\WINDOWS NT\\Curren"...
0x18002032d  mov     rsi, r9
0x180020330  lea     rax, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MSD"...
0x180020337  mov     [r11-38h], rax
0x18002033b  lea     r12, aComComplusDtcS_6; "com\\complus\\dtc\\shared\\util\\vssbac"...
0x180020342  mov     [r11-40h], r13
0x180020346  lea     rax, aInPwszrestorek; "In, pwszRestoreKey = %ws, pwszMsdtcRest"...
0x18002034d  mov     [r11-48h], rax
0x180020351  mov     r9d, 2Bh ; '+'
0x180020357  lea     rax, aIsrestoreneede_0; "IsRestoreNeeded"
0x18002035e  mov     qword ptr [r11-50h], 0
0x180020366  mov     r8, r12
0x180020369  mov     [r11-58h], rax
0x18002036d  lea     edx, [r9-25h]
0x180020371  lea     ecx, [rdx+0Bh]
0x180020374  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180020379  test    rsi, rsi
0x18002037c  jnz     short loc_18002038B
0x18002037e  lea     rcx, aIsrestoreneede_5; "IsRestoreNeeded (com\\complus\\dtc\\sha"...
0x180020385  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18002038b  lea     rax, [rsp+78h+Size]
0x180020393  xor     r14d, r14d
0x180020396  xor     r9d, r9d; unsigned __int8 *
0x180020399  mov     [rsi], r14d
0x18002039c  mov     rdx, r13; unsigned __int16 *
0x18002039f  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800203a4  call    ?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z; ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)
0x1800203a9  mov     ebx, eax
0x1800203ab  mov     edi, 0EAh
0x1800203b0  test    eax, eax
0x1800203b2  jz      short loc_180020425
0x1800203b4  xor     ebp, ebp
0x1800203b6  cmp     eax, 2
0x1800203b9  jnz     short loc_1800203C4
0x1800203bb  xor     ebx, ebx
0x1800203bd  xor     edi, edi
0x1800203bf  jmp     loc_1800205FF
0x1800203c4  cmp     eax, edi
0x1800203c6  jz      short loc_180020425
0x1800203c8  test    eax, eax
0x1800203ca  jle     short loc_1800203D5
0x1800203cc  movzx   ebx, ax
0x1800203cf  or      ebx, 80070000h
0x1800203d5  mov     r9d, 44h ; 'D'; unsigned int
0x1800203db  lea     rdx, aIsrestoreneede_2; "IsRestoreNeeded, ReadRegKeyValue32W(pws"...
0x1800203e2  mov     r8, r12; unsigned __int16 *
0x1800203e5  mov     ecx, ebx; int
0x1800203e7  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800203ec  lea     rax, aReadregkeyvalu_1; "ReadRegKeyValue32W(pwszRestoreKey) to g"...
0x1800203f3  mov     r9d, 45h ; 'E'
0x1800203f9  mov     [rsp+78h+var_48], rax
0x1800203fe  mov     dword ptr [rsp+78h+var_50], ebx
0x180020402  mov     edx, 1
0x180020407  lea     r13, aIsrestoreneede_0; "IsRestoreNeeded"
0x18002040e  mov     r8, r12
0x180020411  mov     [rsp+78h+var_58], r13
0x180020416  lea     ecx, [rdx+10h]
0x180020419  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002041e  xor     edi, edi
0x180020420  jmp     loc_180020606
0x180020425  mov     ecx, dword ptr [rsp+78h+Size]; Size
0x18002042c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020431  mov     rbp, rax
0x180020434  test    rax, rax
0x180020437  jnz     short loc_18002046B
0x180020439  mov     edi, 8007000Eh
0x18002043e  lea     r9d, [rax+4Eh]; unsigned int
0x180020442  mov     ecx, edi; int
0x180020444  lea     rdx, aIsrestoreneede_4; "IsRestoreNeeded, new BYTE[cbSizeOfData]"...
0x18002044b  mov     r8, r12; unsigned __int16 *
0x18002044e  mov     ebx, edi
0x180020450  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180020455  lea     rax, aNewByteCbsizeo; "new BYTE[cbSizeOfData] failed"
0x18002045c  mov     [rsp+78h+var_48], rax
0x180020461  lea     r9d, [rbp+4Fh]
0x180020465  mov     dword ptr [rsp+78h+var_50], edi
0x180020469  jmp     short loc_180020402
0x18002046b  lea     rax, [rsp+78h+Size]
0x180020473  mov     r9, rbp; unsigned __int8 *
0x180020476  mov     rdx, r13; unsigned __int16 *
0x180020479  mov     [rsp+78h+var_58], rax; unsigned int *
0x18002047e  call    ?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z; ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)
0x180020483  mov     ebx, eax
0x180020485  test    eax, eax
0x180020487  jz      short loc_1800204C8
0x180020489  cmp     eax, 2
0x18002048c  jz      loc_1800203BB
0x180020492  test    eax, eax
0x180020494  jle     short loc_18002049F
0x180020496  movzx   ebx, ax
0x180020499  or      ebx, 80070000h
0x18002049f  mov     r9d, 61h ; 'a'; unsigned int
0x1800204a5  lea     rdx, aIsrestoreneede_1; "IsRestoreNeeded, ReadRegKeyValue32W(pws"...
0x1800204ac  mov     r8, r12; unsigned __int16 *
0x1800204af  mov     ecx, ebx; int
0x1800204b1  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800204b6  lea     rax, aReadregkeyvalu_0; "ReadRegKeyValue32W(pwszRestoreKey) to g"...
0x1800204bd  mov     r9d, 62h ; 'b'
0x1800204c3  jmp     loc_1800203F9
0x1800204c8  lea     rax, [rsp+78h+Size]
0x1800204d0  mov     dword ptr [rsp+78h+Size], r14d
0x1800204d8  xor     r9d, r9d; unsigned __int8 *
0x1800204db  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800204e0  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MSD"...
0x1800204e7  call    ?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z; ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)
0x1800204ec  mov     ebx, eax
0x1800204ee  test    eax, eax
0x1800204f0  jz      short loc_18002053B
0x1800204f2  cmp     eax, 2
0x1800204f5  jnz     short loc_180020501
0x1800204f7  xor     ebx, ebx
0x1800204f9  lea     edi, [rbx+1]
0x1800204fc  jmp     loc_1800205FF
0x180020501  cmp     eax, edi
0x180020503  jz      short loc_18002053B
0x180020505  test    eax, eax
0x180020507  jle     short loc_180020512
0x180020509  movzx   ebx, ax
0x18002050c  or      ebx, 80070000h
0x180020512  mov     r9d, 79h ; 'y'; unsigned int
0x180020518  lea     rdx, aIsrestoreneede; "IsRestoreNeeded, ReadRegKeyValue32W(pws"...
0x18002051f  mov     r8, r12; unsigned __int16 *
0x180020522  mov     ecx, ebx; int
0x180020524  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180020529  lea     rax, aReadregkeyvalu; "ReadRegKeyValue32W(pwszMsdtcRestoreKey)"...
0x180020530  mov     r9d, 7Ah ; 'z'
0x180020536  jmp     loc_1800203F9
0x18002053b  mov     ecx, dword ptr [rsp+78h+Size]; Size
0x180020542  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020547  mov     r14, rax
0x18002054a  test    rax, rax
0x18002054d  jnz     short loc_180020588
0x18002054f  mov     edi, 8007000Eh
0x180020554  lea     rdx, aIsrestoreneede_4; "IsRestoreNeeded, new BYTE[cbSizeOfData]"...
0x18002055b  mov     ecx, edi; int
0x18002055d  mov     r9d, 83h; unsigned int
0x180020563  mov     r8, r12; unsigned __int16 *
0x180020566  mov     ebx, edi
0x180020568  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18002056d  lea     rax, aNewByteCbsizeo; "new BYTE[cbSizeOfData] failed"
0x180020574  mov     r9d, 84h
0x18002057a  mov     [rsp+78h+var_48], rax
0x18002057f  mov     dword ptr [rsp+78h+var_50], edi
0x180020583  jmp     loc_180020402
0x180020588  lea     rax, [rsp+78h+Size]
0x180020590  mov     r9, r14; unsigned __int8 *
0x180020593  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MSD"...
0x18002059a  mov     [rsp+78h+var_58], rax; unsigned int *
0x18002059f  call    ?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z; ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)
0x1800205a4  mov     ebx, eax
0x1800205a6  test    eax, eax
0x1800205a8  jz      short loc_1800205E9
0x1800205aa  cmp     eax, 2
0x1800205ad  jz      loc_1800204F7
0x1800205b3  test    eax, eax
0x1800205b5  jle     short loc_1800205C0
0x1800205b7  movzx   ebx, ax
0x1800205ba  or      ebx, 80070000h
0x1800205c0  mov     r9d, 96h; unsigned int
0x1800205c6  lea     rdx, aIsrestoreneede_3; "IsRestoreNeeded, ReadRegKeyValue32W(pws"...
0x1800205cd  mov     r8, r12; unsigned __int16 *
0x1800205d0  mov     ecx, ebx; int
0x1800205d2  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800205d7  lea     rax, aReadregkeyvalu_2; "ReadRegKeyValue32W(pwszMsdtcRestoreKey)"...
0x1800205de  mov     r9d, 97h
0x1800205e4  jmp     loc_1800203F9
0x1800205e9  mov     rdx, r14; lpString2
0x1800205ec  mov     rcx, rbp; lpString1
0x1800205ef  xor     ebx, ebx
0x1800205f1  call    cs:__imp_lstrcmpiW
0x1800205f7  xor     edi, edi
0x1800205f9  test    eax, eax
0x1800205fb  setnz   dil
0x1800205ff  lea     r13, aIsrestoreneede_0; "IsRestoreNeeded"
0x180020606  mov     [rsi], edi
0x180020608  mov     rsi, [rsp+78h+arg_20]
0x180020610  test    rsi, rsi
0x180020613  jz      short loc_180020618
0x180020615  mov     [rsi], rbp
0x180020618  test    ebx, ebx
0x18002061a  js      short loc_180020621
0x18002061c  test    rsi, rsi
0x18002061f  jnz     short loc_180020629
0x180020621  mov     rcx, rbp; Block
0x180020624  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020629  mov     rcx, r14; Block
0x18002062c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020631  test    rsi, rsi
0x180020634  jz      short loc_180020674
0x180020636  mov     rax, [rsi]
0x180020639  test    rax, rax
0x18002063c  jz      short loc_180020674
0x18002063e  mov     [rsp+78h+var_38], rax
0x180020643  mov     edx, 6
0x180020648  mov     dword ptr [rsp+78h+var_40], edi
0x18002064c  lea     rax, aOutBrestorenee_0; "Out, bRestoreNeeded = %d, InstanceValue"...
0x180020653  mov     [rsp+78h+var_48], rax
0x180020658  mov     r9d, 0B3h
0x18002065e  mov     dword ptr [rsp+78h+var_50], ebx
0x180020662  mov     r8, r12
0x180020665  lea     ecx, [rdx+0Bh]
0x180020668  mov     [rsp+78h+var_58], r13
0x18002066d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180020672  jmp     short loc_1800206A3
0x180020674  mov     dword ptr [rsp+78h+var_40], edi
0x180020678  lea     rax, aOutBrestorenee; "Out, bRestoreNeeded = %d"
0x18002067f  mov     [rsp+78h+var_48], rax
0x180020684  mov     edx, 6
0x180020689  mov     dword ptr [rsp+78h+var_50], ebx
0x18002068d  mov     r9d, 0B7h
0x180020693  mov     r8, r12
0x180020696  mov     [rsp+78h+var_58], r13
0x18002069b  lea     ecx, [rdx+0Bh]
0x18002069e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800206a3  lea     r11, [rsp+78h+var_28]
0x1800206a8  mov     eax, ebx
0x1800206aa  mov     rbx, [r11+30h]
0x1800206ae  mov     rbp, [r11+38h]
0x1800206b2  mov     rsp, r11
0x1800206b5  pop     r14
0x1800206b7  pop     r13
0x1800206b9  pop     r12
0x1800206bb  pop     rdi
0x1800206bc  pop     rsi
0x1800206bd  retn
```
