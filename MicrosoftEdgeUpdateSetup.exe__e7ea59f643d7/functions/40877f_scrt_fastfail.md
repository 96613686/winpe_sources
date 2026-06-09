# ___scrt_fastfail

- ea: `0x40877f`
- end: `0x40889a`
- name: `___scrt_fastfail`
- size: `283`
- prototype: `LONG __usercall@<eax>(int@<ebx>, int@<edi>, int@<esi>, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x4081b0`
- `0x408282`
- `0x4084b9`
- `0x408723`
- `0x419500`
- `0x419527`

## callees

- `0x40877f`
- `0x408976`
- `0x409120`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x40878b`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40878b`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x408877`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x408877`
- `KERNEL32!UnhandledExceptionFilter` at `0x408881`
- `KERNEL32!UnhandledExceptionFilter` at `0x408881`
- `KERNEL32!IsDebuggerPresent` at `0x408857`
- `KERNEL32!IsDebuggerPresent` at `0x408857`

## pseudocode

```c
LONG __usercall __scrt_fastfail@<eax>(int a1@<ebx>, int a2@<edi>, int a3@<esi>, unsigned int a4)
{
  void *v4; // eax
  int v5; // ecx
  int v6; // edx
  unsigned int v7; // kr00_4
  BOOL v8; // eax
  bool v9; // bl
  LONG result; // eax
  _DWORD v11[179]; // [esp+8h] [ebp-324h] BYREF
  _DWORD v12[20]; // [esp+2D4h] [ebp-58h] BYREF
  _EXCEPTION_POINTERS ExceptionInfo; // [esp+324h] [ebp-8h] BYREF
  int savedregs; // [esp+32Ch] [ebp+0h]
  _UNKNOWN *retaddr; // [esp+330h] [ebp+4h] BYREF

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(a4);
  sub_408976(3);
  v4 = memset(v11, 0, sizeof(v11));
  v11[44] = v4;
  v11[43] = v5;
  v11[42] = v6;
  v11[41] = a1;
  v11[40] = a3;
  v11[39] = a2;
  LOWORD(v11[50]) = __SS__;
  LOWORD(v11[47]) = __CS__;
  LOWORD(v11[38]) = __DS__;
  LOWORD(v11[37]) = __ES__;
  LOWORD(v11[36]) = __FS__;
  LOWORD(v11[35]) = __GS__;
  v7 = __readeflags();
  v11[48] = v7;
  v11[46] = retaddr;
  v11[49] = &retaddr;
  v11[0] = 65537;
  v11[45] = savedregs;
  memset(v12, 0, sizeof(v12));
  v12[0] = 1073741845;
  v12[1] = 1;
  v12[3] = retaddr;
  v8 = IsDebuggerPresent();
  ExceptionInfo.ExceptionRecord = (PEXCEPTION_RECORD)v12;
  ExceptionInfo.ContextRecord = (PCONTEXT)v11;
  v9 = v8;
  SetUnhandledExceptionFilter(0);
  result = UnhandledExceptionFilter(&ExceptionInfo);
  if ( !result && !v9 )
    return sub_408976(3);
  return result;
}

```

## disassembly

```asm
0x40877f  push    ebp
0x408780  mov     ebp, esp
0x408782  sub     esp, 324h
0x408788  push    ebx
0x408789  push    17h; ProcessorFeature
0x40878b  call    ds:IsProcessorFeaturePresent
0x408791  test    eax, eax
0x408793  jz      short loc_40879A
0x408795  mov     ecx, [ebp+arg_0]
0x408798  int     29h; Win8: RtlFailFast(ecx)
0x40879a  push    3
0x40879c  call    sub_408976
0x4087a1  mov     [esp+32Ch+Size], 2CCh; Size
0x4087a8  lea     eax, [ebp+var_324]
0x4087ae  push    0; Val
0x4087b0  push    eax; void *
0x4087b1  call    _memset
0x4087b6  add     esp, 0Ch
0x4087b9  mov     [ebp+var_274], eax
0x4087bf  mov     [ebp+var_278], ecx
0x4087c5  mov     [ebp+var_27C], edx
0x4087cb  mov     [ebp+var_280], ebx
0x4087d1  mov     [ebp+var_284], esi
0x4087d7  mov     [ebp+var_288], edi
0x4087dd  mov     [ebp+var_25C], ss
0x4087e4  mov     [ebp+var_268], cs
0x4087eb  mov     [ebp+var_28C], ds
0x4087f2  mov     [ebp+var_290], es
0x4087f9  mov     [ebp+var_294], fs
0x408800  mov     [ebp+var_298], gs
0x408807  pushf
0x408808  pop     [ebp+var_264]
0x40880e  mov     eax, [ebp+4]
0x408811  mov     [ebp+var_26C], eax
0x408817  lea     eax, [ebp+4]
0x40881a  mov     [ebp+var_260], eax
0x408820  mov     [ebp+var_324], 10001h
0x40882a  mov     eax, [eax-4]
0x40882d  push    50h ; 'P'; Size
0x40882f  mov     [ebp+var_270], eax
0x408835  lea     eax, [ebp+var_58]
0x408838  push    0; Val
0x40883a  push    eax; void *
0x40883b  call    _memset
0x408840  mov     eax, [ebp+4]
0x408843  add     esp, 0Ch
0x408846  mov     [ebp+var_58], 40000015h
0x40884d  mov     [ebp+var_54], 1
0x408854  mov     [ebp+var_4C], eax
0x408857  call    ds:IsDebuggerPresent
0x40885d  push    0; lpTopLevelExceptionFilter
0x40885f  lea     ebx, [eax-1]
0x408862  neg     ebx
0x408864  lea     eax, [ebp+var_58]
0x408867  mov     [ebp+ExceptionInfo.ExceptionRecord], eax
0x40886a  lea     eax, [ebp+var_324]
0x408870  sbb     bl, bl
0x408872  mov     [ebp+ExceptionInfo.ContextRecord], eax
0x408875  inc     bl
0x408877  call    ds:SetUnhandledExceptionFilter
0x40887d  lea     eax, [ebp+ExceptionInfo]
0x408880  push    eax; ExceptionInfo
0x408881  call    ds:UnhandledExceptionFilter
0x408887  test    eax, eax
0x408889  jnz     short loc_408897
0x40888b  test    bl, bl
0x40888d  jnz     short loc_408897
0x40888f  push    3
0x408891  call    sub_408976
0x408896  pop     ecx
0x408897  pop     ebx
0x408898  leave
0x408899  retn
```
