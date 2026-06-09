# GetDefaultStoragePath

- ea: `0x180007958`
- end: `0x1800079d0`
- name: `GetDefaultStoragePath`
- size: `120`
- prototype: `int __fastcall(PWSTR pszPathOut, size_t cchPathOut)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800078d4`
- `0x180008ac0`

## callees

- `0x18000771c`
- `0x180007958`
- `0x180007bd4`
- `0x18000832c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800079aa`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800079aa`

## string_xrefs

- `0x1800079a1`: `GetDefaultStoragePath`

## pseudocode

```c
int __fastcall GetDefaultStoragePath(PWSTR pszPathOut, size_t cchPathOut)
{
  unsigned int v2; // ebx
  int result; // eax
  int v5; // r8d

  v2 = cchPathOut;
  if ( (unsigned __int8)IsExternalStoragePreferred() )
  {
    result = GetDefaultExternalMosCacheDirectory(pszPathOut, v2);
    if ( result != -2147019873 )
    {
      if ( result >= 0 )
        return result;
      v5 = 264;
      return ZTraceReportPropagationNoThis(result, "GetDefaultStoragePath", v5);
    }
    result = GetInternalMosCacheDirectory(pszPathOut, v2);
    if ( result < 0 )
    {
      v5 = 260;
      return ZTraceReportPropagationNoThis(result, "GetDefaultStoragePath", v5);
    }
  }
  else
  {
    result = GetInternalMosCacheDirectory(pszPathOut, v2);
    if ( result < 0 )
    {
      v5 = 269;
      return ZTraceReportPropagationNoThis(result, "GetDefaultStoragePath", v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007958  mov     [rsp+arg_0], rbx
0x18000795d  push    rdi
0x18000795e  sub     rsp, 20h
0x180007962  mov     ebx, edx
0x180007964  mov     rdi, rcx
0x180007967  call    IsExternalStoragePreferred
0x18000796c  mov     edx, ebx; cchPathOut
0x18000796e  mov     rcx, rdi; pszPathOut
0x180007971  test    al, al
0x180007973  jz      short loc_1800079B2
0x180007975  call    GetDefaultExternalMosCacheDirectory
0x18000797a  cmp     eax, 8007139Fh
0x18000797f  jnz     short loc_180007997
0x180007981  mov     edx, ebx; cchPathOut
0x180007983  mov     rcx, rdi; pszPathOut
0x180007986  call    GetInternalMosCacheDirectory
0x18000798b  test    eax, eax
0x18000798d  jns     short loc_1800079C3
0x18000798f  mov     r8d, 104h
0x180007995  jmp     short loc_1800079A1
0x180007997  test    eax, eax
0x180007999  jns     short loc_1800079C5
0x18000799b  mov     r8d, 108h
0x1800079a1  lea     rdx, aGetdefaultstor; "GetDefaultStoragePath"
0x1800079a8  mov     ecx, eax
0x1800079aa  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800079b0  jmp     short loc_1800079C5
0x1800079b2  call    GetInternalMosCacheDirectory
0x1800079b7  test    eax, eax
0x1800079b9  jns     short loc_1800079C3
0x1800079bb  mov     r8d, 10Dh
0x1800079c1  jmp     short loc_1800079A1
0x1800079c3  xor     eax, eax
0x1800079c5  mov     rbx, [rsp+28h+arg_0]
0x1800079ca  add     rsp, 20h
0x1800079ce  pop     rdi
0x1800079cf  retn
```
