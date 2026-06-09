# ERR_getErrorString

- ea: `0x1802ed700`
- end: `0x1802ed7f7`
- name: `ERR_getErrorString`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1802af120`

## callees

- `0x1802ed700`

## string_xrefs

- `0x1802ed737`: `Unknown frame descriptor`
- `0x1802ed7bf`: `Cannot create Dictionary from provided samples`
- `0x1802ed7e7`: `An I/O error occurred when reading/seeking`

## pseudocode

```c
const char *__fastcall ERR_getErrorString(int a1)
{
  const char *result; // rax

  switch ( a1 )
  {
    case 0:
      result = "No error detected";
      break;
    case 1:
      result = "Error (generic)";
      break;
    case 10:
      result = "Unknown frame descriptor";
      break;
    case 12:
      result = "Version not supported";
      break;
    case 14:
      result = "Unsupported frame parameter";
      break;
    case 16:
      result = "Frame requires too much memory for decoding";
      break;
    case 20:
      result = "Corrupted block detected";
      break;
    case 22:
      result = "Restored data doesn't match checksum";
      break;
    case 30:
      result = "Dictionary is corrupted";
      break;
    case 32:
      result = "Dictionary mismatch";
      break;
    case 34:
      result = "Cannot create Dictionary from provided samples";
      break;
    case 40:
      result = "Unsupported parameter";
      break;
    case 42:
      result = "Parameter is out of bound";
      break;
    case 44:
      result = "tableLog requires too much memory : unsupported";
      break;
    case 46:
      result = "Unsupported max Symbol Value : too large";
      break;
    case 48:
      result = "Specified maxSymbolValue is too small";
      break;
    case 60:
      result = "Operation not authorized at current processing stage";
      break;
    case 62:
      result = "Context should be init first";
      break;
    case 64:
      result = "Allocation error : not enough memory";
      break;
    case 66:
      result = "workSpace buffer is not large enough";
      break;
    case 70:
      result = "Destination buffer is too small";
      break;
    case 72:
      result = "Src size is incorrect";
      break;
    case 74:
      result = "Operation on NULL destination buffer";
      break;
    case 100:
      result = "Frame index is too large";
      break;
    case 102:
      result = "An I/O error occurred when reading/seeking";
      break;
    default:
      result = "Unspecified error code";
      break;
  }
  return result;
}

```

## disassembly

```asm
0x1802ed700  cmp     ecx, 66h; switch 103 cases
0x1802ed703  ja      def_1802ED725; jumptable 00000001802ED725 default case, cases 2-9,11,13,15,17-19,21,23-29,31,33,35-39,41,43,45,47,49-59,61,63,65,67-69,71,73,75-99,101
0x1802ed709  movsxd  rax, ecx
0x1802ed70c  lea     rdx, cs:180000000h
0x1802ed713  movzx   eax, ds:(byte_1802ED860 - 180000000h)[rdx+rax]
0x1802ed71b  mov     ecx, ds:(jpt_1802ED725 - 180000000h)[rdx+rax*4]
0x1802ed722  add     rcx, rdx
0x1802ed725  jmp     rcx; switch jump
0x1802ed727  lea     rax, aNoErrorDetecte; jumptable 00000001802ED725 case 0
0x1802ed72e  retn
0x1802ed72f  lea     rax, aErrorGeneric; jumptable 00000001802ED725 case 1
0x1802ed736  retn
0x1802ed737  lea     rax, aUnknownFrameDe; jumptable 00000001802ED725 case 10
0x1802ed73e  retn
0x1802ed73f  lea     rax, aVersionNotSupp; jumptable 00000001802ED725 case 12
0x1802ed746  retn
0x1802ed747  lea     rax, aUnsupportedFra; jumptable 00000001802ED725 case 14
0x1802ed74e  retn
0x1802ed74f  lea     rax, aFrameRequiresT; jumptable 00000001802ED725 case 16
0x1802ed756  retn
0x1802ed757  lea     rax, aCorruptedBlock; jumptable 00000001802ED725 case 20
0x1802ed75e  retn
0x1802ed75f  lea     rax, aRestoredDataDo; jumptable 00000001802ED725 case 22
0x1802ed766  retn
0x1802ed767  lea     rax, aUnsupportedPar; jumptable 00000001802ED725 case 40
0x1802ed76e  retn
0x1802ed76f  lea     rax, aParameterIsOut; jumptable 00000001802ED725 case 42
0x1802ed776  retn
0x1802ed777  lea     rax, aContextShouldB; jumptable 00000001802ED725 case 62
0x1802ed77e  retn
0x1802ed77f  lea     rax, aAllocationErro; jumptable 00000001802ED725 case 64
0x1802ed786  retn
0x1802ed787  lea     rax, aWorkspaceBuffe; jumptable 00000001802ED725 case 66
0x1802ed78e  retn
0x1802ed78f  lea     rax, aOperationNotAu; jumptable 00000001802ED725 case 60
0x1802ed796  retn
0x1802ed797  lea     rax, aTablelogRequir; jumptable 00000001802ED725 case 44
0x1802ed79e  retn
0x1802ed79f  lea     rax, aUnsupportedMax; jumptable 00000001802ED725 case 46
0x1802ed7a6  retn
0x1802ed7a7  lea     rax, aSpecifiedMaxsy; jumptable 00000001802ED725 case 48
0x1802ed7ae  retn
0x1802ed7af  lea     rax, aDictionaryIsCo; jumptable 00000001802ED725 case 30
0x1802ed7b6  retn
0x1802ed7b7  lea     rax, aDictionaryMism; jumptable 00000001802ED725 case 32
0x1802ed7be  retn
0x1802ed7bf  lea     rax, aCannotCreateDi; jumptable 00000001802ED725 case 34
0x1802ed7c6  retn
0x1802ed7c7  lea     rax, aDestinationBuf; jumptable 00000001802ED725 case 70
0x1802ed7ce  retn
0x1802ed7cf  lea     rax, aSrcSizeIsIncor; jumptable 00000001802ED725 case 72
0x1802ed7d6  retn
0x1802ed7d7  lea     rax, aOperationOnNul; jumptable 00000001802ED725 case 74
0x1802ed7de  retn
0x1802ed7df  lea     rax, aFrameIndexIsTo; jumptable 00000001802ED725 case 100
0x1802ed7e6  retn
0x1802ed7e7  lea     rax, aAnIOErrorOccur; jumptable 00000001802ED725 case 102
0x1802ed7ee  retn
0x1802ed7ef  lea     rax, aUnspecifiedErr; jumptable 00000001802ED725 default case, cases 2-9,11,13,15,17-19,21,23-29,31,33,35-39,41,43,45,47,49-59,61,63,65,67-69,71,73,75-99,101
0x1802ed7f6  retn
```
