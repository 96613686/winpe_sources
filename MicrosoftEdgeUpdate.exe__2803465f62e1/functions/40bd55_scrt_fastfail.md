# ___scrt_fastfail

- ea: `0x40bd55`
- end: `0x40be70`
- name: `___scrt_fastfail`
- size: `283`
- prototype: `LONG __usercall@<eax>(int@<ebx>, int@<edi>, int@<esi>, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x40b630`
- `0x40b702`
- `0x40ba91`
- `0x40bcf3`

## callees

- `0x40bd55`
- `0x40bf56`
- `0x40d0c0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x40be57`
- `KERNEL32!UnhandledExceptionFilter` at `0x40be57`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x40be4d`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x40be4d`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40bd61`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40bd61`
- `KERNEL32!IsDebuggerPresent` at `0x40be2d`
- `KERNEL32!IsDebuggerPresent` at `0x40be2d`

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
  sub_40BF56(3);
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
    return sub_40BF56(3);
  return result;
}

```

## disassembly

```asm
0x40bd55  push    ebp
0x40bd56  mov     ebp, esp
0x40bd58  sub     esp, 324h
0x40bd5e  push    ebx
0x40bd5f  push    17h; ProcessorFeature
0x40bd61  call    ds:IsProcessorFeaturePresent
0x40bd67  test    eax, eax
0x40bd69  jz      short loc_40BD70
0x40bd6b  mov     ecx, [ebp+arg_0]
0x40bd6e  int     29h; Win8: RtlFailFast(ecx)
0x40bd70  push    3
0x40bd72  call    sub_40BF56
0x40bd77  mov     [esp+32Ch+Size], 2CCh; Size
0x40bd7e  lea     eax, [ebp+var_324]
0x40bd84  push    0; Val
0x40bd86  push    eax; void *
0x40bd87  call    _memset
0x40bd8c  add     esp, 0Ch
0x40bd8f  mov     [ebp+var_274], eax
0x40bd95  mov     [ebp+var_278], ecx
0x40bd9b  mov     [ebp+var_27C], edx
0x40bda1  mov     [ebp+var_280], ebx
0x40bda7  mov     [ebp+var_284], esi
0x40bdad  mov     [ebp+var_288], edi
0x40bdb3  mov     [ebp+var_25C], ss
0x40bdba  mov     [ebp+var_268], cs
0x40bdc1  mov     [ebp+var_28C], ds
0x40bdc8  mov     [ebp+var_290], es
0x40bdcf  mov     [ebp+var_294], fs
0x40bdd6  mov     [ebp+var_298], gs
0x40bddd  pushf
0x40bdde  pop     [ebp+var_264]
0x40bde4  mov     eax, [ebp+4]
0x40bde7  mov     [ebp+var_26C], eax
0x40bded  lea     eax, [ebp+4]
0x40bdf0  mov     [ebp+var_260], eax
0x40bdf6  mov     [ebp+var_324], 10001h
0x40be00  mov     eax, [eax-4]
0x40be03  push    50h ; 'P'; Size
0x40be05  mov     [ebp+var_270], eax
0x40be0b  lea     eax, [ebp+var_58]
0x40be0e  push    0; Val
0x40be10  push    eax; void *
0x40be11  call    _memset
0x40be16  mov     eax, [ebp+4]
0x40be19  add     esp, 0Ch
0x40be1c  mov     [ebp+var_58], 40000015h
0x40be23  mov     [ebp+var_54], 1
0x40be2a  mov     [ebp+var_4C], eax
0x40be2d  call    ds:IsDebuggerPresent
0x40be33  push    0; lpTopLevelExceptionFilter
0x40be35  lea     ebx, [eax-1]
0x40be38  neg     ebx
0x40be3a  lea     eax, [ebp+var_58]
0x40be3d  mov     [ebp+ExceptionInfo.ExceptionRecord], eax
0x40be40  lea     eax, [ebp+var_324]
0x40be46  sbb     bl, bl
0x40be48  mov     [ebp+ExceptionInfo.ContextRecord], eax
0x40be4b  inc     bl
0x40be4d  call    ds:SetUnhandledExceptionFilter
0x40be53  lea     eax, [ebp+ExceptionInfo]
0x40be56  push    eax; ExceptionInfo
0x40be57  call    ds:UnhandledExceptionFilter
0x40be5d  test    eax, eax
0x40be5f  jnz     short loc_40BE6D
0x40be61  test    bl, bl
0x40be63  jnz     short loc_40BE6D
0x40be65  push    3
0x40be67  call    sub_40BF56
0x40be6c  pop     ecx
0x40be6d  pop     ebx
0x40be6e  leave
0x40be6f  retn
```
