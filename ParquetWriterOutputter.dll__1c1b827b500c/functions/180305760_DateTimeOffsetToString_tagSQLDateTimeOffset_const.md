# DateTimeOffsetToString(tagSQLDateTimeOffset const &)

- ea: `0x180305760`
- end: `0x1803059af`
- name: `?DateTimeOffsetToString@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUtagSQLDateTimeOffset@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014240`

## callees

- `0x18001ca80`
- `0x180026660`
- `0x180305760`
- `0x18030c190`
- `0x1803456a0`

## string_xrefs

- `0x1803057c8`: `c:\source\src\common\types.cpp`
- `0x1803057eb`: `c:\source\src\common\types.cpp`
- `0x18030580d`: `c:\source\src\common\types.cpp`
- `0x180305830`: `c:\source\src\common\types.cpp`
- `0x18030586d`: `c:\source\src\common\types.cpp`
- `0x180305890`: `c:\source\src\common\types.cpp`
- `0x1803058b2`: `c:\source\src\common\types.cpp`
- `0x1803058d4`: `c:\source\src\common\types.cpp`
- `0x1803058f7`: `c:\source\src\common\types.cpp`

## pseudocode

```c
_QWORD *__fastcall DateTimeOffsetToString(_QWORD *a1, __int16 *a2)
{
  __int16 v4; // ax
  __int16 v5; // cx
  __int16 v6; // ax
  unsigned __int8 v7; // cl
  int v8; // edx
  bool v9; // cc
  char *v10; // r11

  _CheckForDebuggerJustMyCode(qword_1804EA208);
  std::string::string(a1, 0x22u);
  v4 = a2[8];
  if ( v4 < 0 || (v5 = a2[9], v5 < 0) )
  {
    v9 = v4 < -14;
    if ( v4 == -14 )
    {
      v4 = -14;
      if ( a2[9] )
        wassert(
          L"sqlDateTimeOffset.timezone_hour != -14 || sqlDateTimeOffset.timezone_minute == 0",
          L"c:\\source\\src\\common\\types.cpp",
          0x167u);
      v9 = 0;
    }
    if ( v9 )
      wassert(L"sqlDateTimeOffset.timezone_hour >= -14", L"c:\\source\\src\\common\\types.cpp", 0x168u);
    if ( v4 > 0 )
      wassert(L"sqlDateTimeOffset.timezone_hour <= 0", L"c:\\source\\src\\common\\types.cpp", 0x169u);
    v6 = a2[9];
    if ( v6 > 0 )
      wassert(L"sqlDateTimeOffset.timezone_minute <= 0", L"c:\\source\\src\\common\\types.cpp", 0x16Au);
    if ( v6 < -59 )
      wassert(L"sqlDateTimeOffset.timezone_minute >= -59", L"c:\\source\\src\\common\\types.cpp", 0x16Bu);
    v8 = 45;
    v7 = -*((_BYTE *)a2 + 16);
    LOBYTE(v6) = -(char)v6;
  }
  else
  {
    if ( v4 == 14 )
    {
      if ( v5 )
        wassert(
          L"sqlDateTimeOffset.timezone_hour != 14 || sqlDateTimeOffset.timezone_minute == 0",
          L"c:\\source\\src\\common\\types.cpp",
          0x15Bu);
    }
    else if ( v4 > 14 )
    {
      wassert(L"sqlDateTimeOffset.timezone_hour <= 14", L"c:\\source\\src\\common\\types.cpp", 0x15Cu);
    }
    v6 = a2[9];
    if ( v6 < 0 )
      wassert(L"sqlDateTimeOffset.timezone_minute >= 0", L"c:\\source\\src\\common\\types.cpp", 0x15Du);
    if ( v6 > 59 )
      wassert(L"sqlDateTimeOffset.timezone_minute <= 59", L"c:\\source\\src\\common\\types.cpp", 0x15Eu);
    v7 = *((_BYTE *)a2 + 16);
    v8 = 43;
  }
  v10 = (char *)a1;
  if ( a1[3] >= 0x10u )
    v10 = (char *)*a1;
  sprintf_s(
    v10,
    a1[2] + 1LL,
    "%04u-%02u-%02u %02u:%02u:%02u.%07u %c%02u:%02u",
    *a2,
    (unsigned __int16)a2[1],
    (unsigned __int16)a2[2],
    (unsigned __int16)a2[3],
    (unsigned __int16)a2[4],
    (unsigned __int16)a2[5],
    *((_DWORD *)a2 + 3),
    v8,
    v7,
    (unsigned __int8)v6);
  return a1;
}

```

## disassembly

```asm
0x180305760  mov     [rsp+arg_0], rbx
0x180305765  mov     [rsp+arg_8], rbp
0x18030576a  mov     [rsp+arg_10], rsi
0x18030576f  push    rdi
0x180305770  push    r12
0x180305772  push    r13
0x180305774  push    r14
0x180305776  push    r15
0x180305778  sub     rsp, 70h
0x18030577c  mov     rdi, rcx
0x18030577f  mov     rbx, rdx
0x180305782  lea     rcx, qword_1804EA208
0x180305789  call    __CheckForDebuggerJustMyCode
0x18030578e  xor     r8d, r8d
0x180305791  mov     rcx, rdi; void *
0x180305794  lea     edx, [r8+22h]; Size
0x180305798  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x18030579d  movzx   eax, word ptr [rbx+10h]
0x1803057a1  test    ax, ax
0x1803057a4  js      loc_180305855
0x1803057aa  movzx   ecx, word ptr [rbx+12h]
0x1803057ae  test    cx, cx
0x1803057b1  js      loc_180305855
0x1803057b7  cmp     ax, 0Eh
0x1803057bb  jnz     short loc_1803057E3
0x1803057bd  test    cx, cx
0x1803057c0  jz      short loc_1803057FE
0x1803057c2  mov     r8d, 15Bh; Line
0x1803057c8  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x1803057cf  lea     rcx, aSqldatetimeoff_7; "sqlDateTimeOffset.timezone_hour != 14 |"...
0x1803057d6  call    _wassert
0x1803057db  movzx   eax, word ptr [rbx+10h]
0x1803057df  cmp     ax, 0Eh
0x1803057e3  jle     short loc_1803057FE
0x1803057e5  mov     r8d, 15Ch; Line
0x1803057eb  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x1803057f2  lea     rcx, aSqldatetimeoff_6; "sqlDateTimeOffset.timezone_hour <= 14"
0x1803057f9  call    _wassert
0x1803057fe  movzx   eax, word ptr [rbx+12h]
0x180305802  test    ax, ax
0x180305805  jns     short loc_180305824
0x180305807  mov     r8d, 15Dh; Line
0x18030580d  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x180305814  lea     rcx, aSqldatetimeoff_4; "sqlDateTimeOffset.timezone_minute >= 0"
0x18030581b  call    _wassert
0x180305820  movzx   eax, word ptr [rbx+12h]
0x180305824  cmp     ax, 3Bh ; ';'
0x180305828  jle     short loc_180305847
0x18030582a  mov     r8d, 15Eh; Line
0x180305830  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x180305837  lea     rcx, aSqldatetimeoff_2; "sqlDateTimeOffset.timezone_minute <= 59"
0x18030583e  call    _wassert
0x180305843  movzx   eax, byte ptr [rbx+12h]
0x180305847  movzx   ecx, byte ptr [rbx+10h]
0x18030584b  mov     edx, 2Bh ; '+'
0x180305850  jmp     loc_18030591B
0x180305855  cmp     ax, 0FFF2h
0x180305859  jnz     short loc_180305888
0x18030585b  cmp     word ptr [rbx+12h], 0
0x180305860  mov     eax, 0FFFFFFF2h
0x180305865  jz      short loc_180305884
0x180305867  mov     r8d, 167h; Line
0x18030586d  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x180305874  lea     rcx, aSqldatetimeoff_0; "sqlDateTimeOffset.timezone_hour != -14 "...
0x18030587b  call    _wassert
0x180305880  movzx   eax, word ptr [rbx+10h]
0x180305884  cmp     ax, 0FFF2h
0x180305888  jge     short loc_1803058A7
0x18030588a  mov     r8d, 168h; Line
0x180305890  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x180305897  lea     rcx, aSqldatetimeoff_1; "sqlDateTimeOffset.timezone_hour >= -14"
0x18030589e  call    _wassert
0x1803058a3  movzx   eax, word ptr [rbx+10h]
0x1803058a7  test    ax, ax
0x1803058aa  jle     short loc_1803058C5
0x1803058ac  mov     r8d, 169h; Line
0x1803058b2  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x1803058b9  lea     rcx, aSqldatetimeoff; "sqlDateTimeOffset.timezone_hour <= 0"
0x1803058c0  call    _wassert
0x1803058c5  movzx   eax, word ptr [rbx+12h]
0x1803058c9  test    ax, ax
0x1803058cc  jle     short loc_1803058EB
0x1803058ce  mov     r8d, 16Ah; Line
0x1803058d4  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x1803058db  lea     rcx, aSqldatetimeoff_5; "sqlDateTimeOffset.timezone_minute <= 0"
0x1803058e2  call    _wassert
0x1803058e7  movzx   eax, word ptr [rbx+12h]
0x1803058eb  cmp     ax, 0FFC5h
0x1803058ef  jge     short loc_18030590E
0x1803058f1  mov     r8d, 16Bh; Line
0x1803058f7  lea     rdx, aCSourceSrcComm; "c:\\source\\src\\common\\types.cpp"
0x1803058fe  lea     rcx, aSqldatetimeoff_3; "sqlDateTimeOffset.timezone_minute >= -5"...
0x180305905  call    _wassert
0x18030590a  movzx   eax, byte ptr [rbx+12h]
0x18030590e  movzx   ecx, byte ptr [rbx+10h]
0x180305912  mov     edx, 2Dh ; '-'
0x180305917  neg     cl
0x180305919  neg     al
0x18030591b  cmp     qword ptr [rdi+18h], 10h
0x180305920  mov     r11, rdi
0x180305923  mov     esi, [rbx+0Ch]
0x180305926  movzx   ebp, word ptr [rbx+0Ah]
0x18030592a  movzx   r14d, word ptr [rbx+8]
0x18030592f  movzx   r15d, word ptr [rbx+6]
0x180305934  movzx   r12d, word ptr [rbx+4]
0x180305939  movzx   r13d, word ptr [rbx+2]
0x18030593e  movsx   r9d, word ptr [rbx]
0x180305942  mov     r10, [rdi+10h]
0x180305946  jb      short loc_18030594B
0x180305948  mov     r11, [rdi]
0x18030594b  movzx   r8d, cl
0x18030594f  mov     rcx, r11; Buffer
0x180305952  movzx   eax, al
0x180305955  mov     [rsp+98h+var_38], eax
0x180305959  mov     [rsp+98h+var_40], r8d
0x18030595e  lea     r8, a04u02u02u02u02; "%04u-%02u-%02u %02u:%02u:%02u.%07u %c%0"...
0x180305965  mov     [rsp+98h+var_48], edx
0x180305969  lea     rdx, [r10+1]; BufferCount
0x18030596d  mov     [rsp+98h+var_50], esi
0x180305971  mov     [rsp+98h+var_58], ebp
0x180305975  mov     [rsp+98h+var_60], r14d
0x18030597a  mov     [rsp+98h+var_68], r15d
0x18030597f  mov     [rsp+98h+var_70], r12d
0x180305984  mov     [rsp+98h+var_78], r13d
0x180305989  call    sprintf_s
0x18030598e  lea     r11, [rsp+98h+var_28]
0x180305993  mov     rax, rdi
0x180305996  mov     rbx, [r11+30h]
0x18030599a  mov     rbp, [r11+38h]
0x18030599e  mov     rsi, [r11+40h]
0x1803059a2  mov     rsp, r11
0x1803059a5  pop     r15
0x1803059a7  pop     r14
0x1803059a9  pop     r13
0x1803059ab  pop     r12
0x1803059ad  pop     rdi
0x1803059ae  retn
```
