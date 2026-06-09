# WriteOtherSubrs

- ea: `0x18004b8a0`
- end: `0x18004bb18`
- name: `WriteOtherSubrs`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004bb20`

## callees

- `0x180048e0c`
- `0x180049e14`
- `0x18004a110`
- `0x18004a3b4`
- `0x18004b8a0`

## string_xrefs

- `0x18004b9a1`: `{pop 0}\n{/internaldict errordict /invalidaccess get exec}\nifelse\n}\ndup 14 get 1 25 dict put\nbind executeonly put\n} if\n1183615869 userdict /internaldict get exec\n/FlxProc known {save true} {false} ifelse}\nifelse\n`
- `0x18004b992`: `[systemdict /internaldict known\n{1183615869 systemdict /internaldict get exec\n/FlxProc known {save true} {false} ifelse}\n{userdict /internaldict known not {\nuserdict /internaldict\n{count 0 eq\n{/internaldict errordict /invalidaccess get exec} if\ndup type /integertype ne\n{/internaldict errordict /invalidaccess get exec} if\ndup 1183615869 eq\n`
- `0x18004ba73`: `exch /FlxProc exch put true}\nifelse}\nifelse}\nifelse\n{systemdict /internaldict known\n{{1183615869 systemdict /internaldict get exec /FlxProc get exec}}\n{{1183615869 userdict /internaldict get exec /FlxProc get exec}}\nifelse executeonly\n} if\n{gsave currentpoint newpath moveto} executeonly \n`
- `0x18004ba82`: `{currentpoint grestore gsave currentpoint newpath moveto}\nexecuteonly \n`

## pseudocode

```c
void __fastcall WriteOtherSubrs(__int64 a1, int a2, int a3)
{
  __int64 i; // rdi
  __int64 v7; // rdx
  const char *v8; // rdx
  const char *v9; // rdx
  const char *v10; // rdx
  const char *v11; // rdx

  if ( *(_QWORD *)(a1 + 8016) )
  {
    PutString(a1, "/OtherSubrs [\r\n");
    for ( i = 0; i != 4; ++i )
    {
      PutString(a1, "{");
      v7 = *(_QWORD *)(*(_QWORD *)(a1 + 8016) + 8 * i);
      if ( v7 )
      {
        PutString(a1, v7);
        v8 = "}executeonly";
      }
      else
      {
        v8 = "}";
      }
      PutString(a1, v8);
    }
    if ( *(_DWORD *)(a1 + 488) )
    {
      PutString(a1, "{} {} {}\r\n");
      PutString(a1, "{} {} {} {} {} {} {} \r\n");
      WriteBlendOtherSubrs(a1);
      if ( (unsigned int)XCF_TransDesignFont(a1) )
        WriteAdditionalOtherSubrs(a1);
    }
    v9 = "] |-\r\n";
LABEL_23:
    PutString(a1, v9);
    return;
  }
  if ( a2 || a3 || *(_DWORD *)(a1 + 488) )
  {
    PutString(a1, "/OtherSubrs\r\n");
    if ( a2 )
    {
      PutString(
        a1,
        "[systemdict /internaldict known\r\n"
        "{1183615869 systemdict /internaldict get exec\r\n"
        "/FlxProc known {save true} {false} ifelse}\r\n"
        "{userdict /internaldict known not {\r\n"
        "userdict /internaldict\r\n"
        "{count 0 eq\r\n"
        "{/internaldict errordict /invalidaccess get exec} if\r\n"
        "dup type /integertype ne\r\n"
        "{/internaldict errordict /invalidaccess get exec} if\r\n"
        "dup 1183615869 eq\r\n");
      PutString(
        a1,
        "{pop 0}\r\n"
        "{/internaldict errordict /invalidaccess get exec}\r\n"
        "ifelse\r\n"
        "}\r\n"
        "dup 14 get 1 25 dict put\r\n"
        "bind executeonly put\r\n"
        "} if\r\n"
        "1183615869 userdict /internaldict get exec\r\n"
        "/FlxProc known {save true} {false} ifelse}\r\n"
        "ifelse\r\n");
      PutString(
        a1,
        "[\r\n"
        "systemdict /internaldict known not\r\n"
        "{ 100 dict /begin cvx /mtx matrix /def cvx } if\r\n"
        "systemdict /currentpacking known {currentpacking true setpacking} if\r\n"
        "{\r\n"
        "systemdict /internaldict known {\r\n"
        "1183615869 systemdict /internaldict get exec\r\n"
        "dup /$FlxDict known not {\r\n"
        "dup dup length exch maxlength eq\r\n"
        "{ pop userdict dup /$FlxDict known not\r\n");
      PutString(
        a1,
        "{ 100 dict begin /mtx matrix def\r\n"
        "dup /$FlxDict currentdict put end } if }\r\n"
        "{ 100 dict begin /mtx matrix def\r\n"
        "dup /$FlxDict currentdict put end }\r\n"
        "ifelse\r\n"
        "} if /$FlxDict get begin } if\r\n"
        "grestore\r\n"
        "/exdef {exch def} def\r\n"
        "/dmin exch abs 100 div def\r\n"
        "/epX exdef /epY exdef\r\n");
      PutString(
        a1,
        "/c4y2 exdef /c4x2 exdef /c4y1 exdef /c4x1 exdef /c4y0 exdef /c4x0 exdef\r\n"
        "/c3y2 exdef /c3x2 exdef /c3y1 exdef /c3x1 exdef /c3y0 exdef /c3x0 exdef\r\n"
        "/c1y2 exdef /c1x2 exdef /c2x2 c4x2 def /c2y2 c4y2 def\r\n"
        "/yflag c1y2 c3y2 sub abs c1x2 c3x2 sub abs gt def\r\n"
        "/PickCoords { \r\n"
        "{c1x0 c1y0 c1x1 c1y1 c1x2 c1y2 c2x0 c2y0 c2x1 c2y1 c2x2 c2y2}\r\n"
        "{c3x0 c3y0 c3x1 c3y1 c3x2 c3y2 c4x0 c4y0 c4x1 c4y1 c4x2 c4y2}\r\n"
        "ifelse\r\n"
        "/y5 exdef /x5 exdef /y4 exdef /x4 exdef /y3 exdef /x3 exdef\r\n"
        "/y2 exdef /x2 exdef /y1 exdef /x1 exdef /y0 exdef /x0 exdef\r\n");
      PutString(
        a1,
        "} def\r\n"
        "mtx currentmatrix pop \r\n"
        "mtx 0 get abs .00001 lt mtx 3 get abs .00001 lt or\r\n"
        "{/flipXY -1 def}\r\n"
        "{mtx 1 get abs .00001 lt mtx 2 get abs .00001 lt or\r\n"
        "{/flipXY 1 def}\r\n"
        "{/flipXY 0 def}\r\n"
        "ifelse }\r\n"
        "ifelse\r\n"
        "/erosion 1 def \r\n");
      PutString(
        a1,
        "systemdict /internaldict known {\r\n"
        " 1183615869 systemdict /internaldict get exec dup \r\n"
        "/erosion known\r\n"
        "{/erosion get /erosion exch def}\r\n"
        "{pop}\r\n"
        "ifelse\r\n"
        "} if\r\n"
        "yflag\r\n"
        "{flipXY 0 eq c3y2 c4y2 eq or\r\n"
        "{false PickCoords}\r\n");
      PutString(
        a1,
        "{/shrink c3y2 c4y2 eq\r\n"
        "{0}{c1y2 c4y2 sub c3y2 c4y2 sub div abs} ifelse def\r\n"
        "/yshrink {c4y2 sub shrink mul c4y2 add} def\r\n"
        "/c1y0 c3y0 yshrink def /c1y1 c3y1 yshrink def\r\n"
        "/c2y0 c4y0 yshrink def /c2y1 c4y1 yshrink def\r\n"
        "/c1x0 c3x0 def /c1x1 c3x1 def /c2x0 c4x0 def /c2x1 c4x1 def\r\n"
        "/dY 0 c3y2 c1y2 sub round\r\n"
        "dtransform flipXY 1 eq {exch} if pop abs def\r\n"
        "dY dmin lt PickCoords\r\n"
        "y2 c1y2 sub abs 0.001 gt {\r\n");
      PutString(
        a1,
        "c1x2 c1y2 transform flipXY 1 eq {exch} if \r\n"
        "/cx exch def /cy exch def\r\n"
        "/dY 0 y2 c1y2 sub round dtransform flipXY 1 eq {exch}\r\n"
        "if pop def\r\n"
        "dY round dup 0 ne\r\n"
        "{/dY exdef }\r\n"
        "{pop dY 0 lt {-1}{1} ifelse /dY exdef}\r\n"
        "ifelse\r\n"
        "/erode PaintType 2 ne erosion 0.5 ge and def\r\n"
        "erode {/cy cy 0.5 sub def} if\r\n");
      PutString(
        a1,
        "/ey cy dY add def \r\n"
        "/ey ey ceiling ey sub ey floor add def \r\n"
        "erode {/ey ey 0.5 add def} if \r\n"
        "ey cx flipXY 1 eq {exch} if itransform exch pop\r\n"
        "y2 sub /eShift exch def\r\n"
        "/y1 y1 eShift add def /y2 y2 eShift add def /y3 y3\r\n"
        "eShift add def\r\n"
        "} if\r\n"
        "} ifelse\r\n"
        "}\r\n");
      PutString(
        a1,
        "{flipXY 0 eq c3x2 c4x2 eq or\r\n"
        "{false PickCoords }\r\n"
        "{/shrink c3x2 c4x2 eq\r\n"
        "{0}{c1x2 c4x2 sub c3x2 c4x2 sub div abs} ifelse def\r\n"
        "/xshrink {c4x2 sub shrink mul c4x2 add} def\r\n"
        "/c1x0 c3x0 xshrink def /c1x1 c3x1 xshrink def\r\n"
        "/c2x0 c4x0 xshrink def /c2x1 c4x1 xshrink def\r\n"
        "/c1y0 c3y0 def /c1y1 c3y1 def /c2y0 c4y0 def /c2y1 c4y1 def\r\n"
        "/dX c3x2 c1x2 sub round 0 dtransform\r\n"
        "flipXY -1 eq {exch} if pop abs def\r\n");
      PutString(
        a1,
        "dX dmin lt PickCoords\r\n"
        "x2 c1x2 sub abs 0.001 gt {\r\n"
        "c1x2 c1y2 transform flipXY -1 eq {exch} if\r\n"
        "/cy exch def /cx exch def \r\n"
        "/dX x2 c1x2 sub round 0 dtransform flipXY -1 eq {exch} if pop def\r\n"
        "dX round dup 0 ne\r\n"
        "{/dX exdef}\r\n"
        "{pop dX 0 lt {-1}{1} ifelse /dX exdef}\r\n"
        "ifelse\r\n"
        "/erode PaintType 2 ne erosion .5 ge and def\r\n");
      PutString(
        a1,
        "erode {/cx cx .5 sub def} if\r\n"
        "/ex cx dX add def\r\n"
        "/ex ex ceiling ex sub ex floor add def\r\n"
        "erode {/ex ex .5 add def} if\r\n"
        "ex cy flipXY -1 eq {exch} if itransform pop\r\n"
        "x2 sub /eShift exch def\r\n"
        "/x1 x1 eShift add def /x2 x2 eShift add def /x3 x3 eShift add def\r\n"
        "} if\r\n"
        "} ifelse\r\n"
        "} ifelse\r\n");
      PutString(
        a1,
        "x2 x5 eq y2 y5 eq or\r\n"
        "{x5 y5 lineto }\r\n"
        "{x0 y0 x1 y1 x2 y2 curveto\r\n"
        "x3 y3 x4 y4 x5 y5 curveto}\r\n"
        "ifelse\r\n"
        "epY epX \r\n"
        "}\r\n"
        "systemdict /currentpacking known {exch setpacking} if \r\n"
        "/exec cvx /end cvx ] cvx\r\n"
        "executeonly\r\n");
      PutString(
        a1,
        "exch\r\n"
        "{pop true exch restore} \r\n"
        "{ \r\n"
        "systemdict /internaldict known not\r\n"
        "{1183615869 userdict /internaldict get exec\r\n"
        "exch /FlxProc exch put true}\r\n"
        "{1183615869 systemdict /internaldict get exec\r\n"
        "dup length exch maxlength eq\r\n"
        "{false} \r\n"
        "{1183615869 systemdict /internaldict get exec\r\n");
      PutString(
        a1,
        "exch /FlxProc exch put true}\r\n"
        "ifelse}\r\n"
        "ifelse}\r\n"
        "ifelse\r\n"
        "{systemdict /internaldict known\r\n"
        "{{1183615869 systemdict /internaldict get exec /FlxProc get exec}}\r\n"
        "{{1183615869 userdict /internaldict get exec /FlxProc get exec}}\r\n"
        "ifelse executeonly\r\n"
        "} if\r\n"
        "{gsave currentpoint newpath moveto} executeonly \r\n");
      v10 = "{currentpoint grestore gsave currentpoint newpath moveto}\r\nexecuteonly \r\n";
    }
    else
    {
      v10 = "[ {} {} {}\r\n";
    }
    PutString(a1, v10);
    v11 = "{\r\n"
          "systemdict /internaldict known not\r\n"
          "{pop 3}\r\n"
          "{1183615869 systemdict /internaldict get exec\r\n"
          " dup /startlock known\r\n"
          " {/startlock get exec}\r\n"
          " {dup /strtlck known\r\n"
          " {/strtlck get exec}\r\n"
          " {pop 3}\r\n"
          " ifelse}\r\n"
          " ifelse}\r\n"
          " ifelse\r\n"
          "} executeonly\r\n";
    if ( !a3 )
      v11 = "{}\r\n";
    PutString(a1, v11);
    PutString(a1, "{} {} {}\r\n");
    if ( *(_DWORD *)(a1 + 488) )
    {
      PutString(a1, "{} {} {} {} {} {} {} \r\n");
      WriteBlendOtherSubrs(a1);
      if ( (unsigned int)XCF_TransDesignFont(a1) )
        WriteAdditionalOtherSubrs(a1);
    }
    v9 = "]|-\r\n";
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x18004b8a0  mov     [rsp+arg_0], rbx
0x18004b8a5  mov     [rsp+arg_8], rsi
0x18004b8aa  push    rdi
0x18004b8ab  sub     rsp, 20h
0x18004b8af  cmp     qword ptr [rcx+1F50h], 0
0x18004b8b7  mov     esi, r8d
0x18004b8ba  mov     edi, edx
0x18004b8bc  mov     rbx, rcx
0x18004b8bf  jz      loc_18004B96A
0x18004b8c5  lea     rdx, aOthersubrs; "/OtherSubrs [\r\n"
0x18004b8cc  call    PutString
0x18004b8d1  xor     edi, edi
0x18004b8d3  lea     rdx, asc_180068E88; "{"
0x18004b8da  mov     rcx, rbx
0x18004b8dd  call    PutString
0x18004b8e2  mov     rax, [rbx+1F50h]
0x18004b8e9  mov     rdx, [rax+rdi*8]
0x18004b8ed  test    rdx, rdx
0x18004b8f0  jz      short loc_18004B903
0x18004b8f2  mov     rcx, rbx
0x18004b8f5  call    PutString
0x18004b8fa  lea     rdx, aExecuteonly; "}executeonly"
0x18004b901  jmp     short loc_18004B90A
0x18004b903  lea     rdx, asc_180068C28; "}"
0x18004b90a  mov     rcx, rbx
0x18004b90d  call    PutString
0x18004b912  inc     rdi
0x18004b915  cmp     rdi, 4
0x18004b919  jnz     short loc_18004B8D3
0x18004b91b  cmp     dword ptr [rbx+1E8h], 0
0x18004b922  jz      short loc_18004B95E
0x18004b924  lea     rdx, asc_180068EA8; "{} {} {}\r\n"
0x18004b92b  mov     rcx, rbx
0x18004b92e  call    PutString
0x18004b933  lea     rdx, asc_180068E90; "{} {} {} {} {} {} {} \r\n"
0x18004b93a  mov     rcx, rbx
0x18004b93d  call    PutString
0x18004b942  mov     rcx, rbx
0x18004b945  call    WriteBlendOtherSubrs
0x18004b94a  mov     rcx, rbx
0x18004b94d  call    XCF_TransDesignFont
0x18004b952  test    eax, eax
0x18004b954  jz      short loc_18004B95E
0x18004b956  mov     rcx, rbx
0x18004b959  call    WriteAdditionalOtherSubrs
0x18004b95e  lea     rdx, asc_180068EC8; "] |-\r\n"
0x18004b965  jmp     loc_18004BB00
0x18004b96a  test    edi, edi
0x18004b96c  jnz     short loc_18004B97E
0x18004b96e  test    esi, esi
0x18004b970  jnz     short loc_18004B97E
0x18004b972  cmp     [rcx+1E8h], esi
0x18004b978  jz      loc_18004BB08
0x18004b97e  lea     rdx, aOthersubrs_0; "/OtherSubrs\r\n"
0x18004b985  call    PutString
0x18004b98a  test    edi, edi
0x18004b98c  jz      loc_18004BA8B
0x18004b992  lea     rdx, aSystemdictInte_2; "[systemdict /internaldict known\r\n{118"...
0x18004b999  mov     rcx, rbx
0x18004b99c  call    PutString
0x18004b9a1  lea     rdx, aPop0Internaldi; "{pop 0}\r\n{/internaldict errordict /in"...
0x18004b9a8  mov     rcx, rbx
0x18004b9ab  call    PutString
0x18004b9b0  lea     rdx, aSystemdictInte_3; "[\r\nsystemdict /internaldict known not"...
0x18004b9b7  mov     rcx, rbx
0x18004b9ba  call    PutString
0x18004b9bf  lea     rdx, a100DictBeginMt; "{ 100 dict begin /mtx matrix def\r\ndup"...
0x18004b9c6  mov     rcx, rbx
0x18004b9c9  call    PutString
0x18004b9ce  lea     rdx, aC4y2ExdefC4x2E; "/c4y2 exdef /c4x2 exdef /c4y1 exdef /c4"...
0x18004b9d5  mov     rcx, rbx
0x18004b9d8  call    PutString
0x18004b9dd  lea     rdx, aDefMtxCurrentm; "} def\r\nmtx currentmatrix pop \r\nmtx "...
0x18004b9e4  mov     rcx, rbx
0x18004b9e7  call    PutString
0x18004b9ec  lea     rdx, aSystemdictInte_1; "systemdict /internaldict known {\r\n 11"...
0x18004b9f3  mov     rcx, rbx
0x18004b9f6  call    PutString
0x18004b9fb  lea     rdx, aShrinkC3y2C4y2; "{/shrink c3y2 c4y2 eq\r\n{0}{c1y2 c4y2 "...
0x18004ba02  mov     rcx, rbx
0x18004ba05  call    PutString
0x18004ba0a  lea     rdx, aC1x2C1y2Transf; "c1x2 c1y2 transform flipXY 1 eq {exch} "...
0x18004ba11  mov     rcx, rbx
0x18004ba14  call    PutString
0x18004ba19  lea     rdx, aEyCyDyAddDefEy; "/ey cy dY add def \r\n/ey ey ceiling ey"...
0x18004ba20  mov     rcx, rbx
0x18004ba23  call    PutString
0x18004ba28  lea     rdx, aFlipxy0EqC3x2C; "{flipXY 0 eq c3x2 c4x2 eq or\r\n{false "...
0x18004ba2f  mov     rcx, rbx
0x18004ba32  call    PutString
0x18004ba37  lea     rdx, aDxDminLtPickco; "dX dmin lt PickCoords\r\nx2 c1x2 sub ab"...
0x18004ba3e  mov     rcx, rbx
0x18004ba41  call    PutString
0x18004ba46  lea     rdx, aErodeCxCx5SubD; "erode {/cx cx .5 sub def} if\r\n/ex cx "...
0x18004ba4d  mov     rcx, rbx
0x18004ba50  call    PutString
0x18004ba55  lea     rdx, aX2X5EqY2Y5EqOr; "x2 x5 eq y2 y5 eq or\r\n{x5 y5 lineto }"...
0x18004ba5c  mov     rcx, rbx
0x18004ba5f  call    PutString
0x18004ba64  lea     rdx, aExchPopTrueExc; "exch\r\n{pop true exch restore} \r\n{ "...
0x18004ba6b  mov     rcx, rbx
0x18004ba6e  call    PutString
0x18004ba73  lea     rdx, aExchFlxprocExc; "exch /FlxProc exch put true}\r\nifelse}"...
0x18004ba7a  mov     rcx, rbx
0x18004ba7d  call    PutString
0x18004ba82  lea     rdx, aCurrentpointGr; "{currentpoint grestore gsave currentpoi"...
0x18004ba89  jmp     short loc_18004BA92
0x18004ba8b  lea     rdx, asc_18006A250; "[ {} {} {}\r\n"
0x18004ba92  mov     rcx, rbx
0x18004ba95  call    PutString
0x18004ba9a  lea     rax, asc_180068C78; "{}\r\n"
0x18004baa1  test    esi, esi
0x18004baa3  lea     rdx, aSystemdictInte; "{\r\nsystemdict /internaldict known not"...
0x18004baaa  mov     rcx, rbx
0x18004baad  cmovz   rdx, rax
0x18004bab1  call    PutString
0x18004bab6  lea     rdx, asc_180068EA8; "{} {} {}\r\n"
0x18004babd  mov     rcx, rbx
0x18004bac0  call    PutString
0x18004bac5  cmp     dword ptr [rbx+1E8h], 0
0x18004bacc  jz      short loc_18004BAF9
0x18004bace  lea     rdx, asc_180068E90; "{} {} {} {} {} {} {} \r\n"
0x18004bad5  mov     rcx, rbx
0x18004bad8  call    PutString
0x18004badd  mov     rcx, rbx
0x18004bae0  call    WriteBlendOtherSubrs
0x18004bae5  mov     rcx, rbx
0x18004bae8  call    XCF_TransDesignFont
0x18004baed  test    eax, eax
0x18004baef  jz      short loc_18004BAF9
0x18004baf1  mov     rcx, rbx
0x18004baf4  call    WriteAdditionalOtherSubrs
0x18004baf9  lea     rdx, asc_18006A2AC; "]|-\r\n"
0x18004bb00  mov     rcx, rbx
0x18004bb03  call    PutString
0x18004bb08  mov     rbx, [rsp+28h+arg_0]
0x18004bb0d  mov     rsi, [rsp+28h+arg_8]
0x18004bb12  add     rsp, 20h
0x18004bb16  pop     rdi
0x18004bb17  retn
```
