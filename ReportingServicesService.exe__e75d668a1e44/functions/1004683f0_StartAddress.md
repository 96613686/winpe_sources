# StartAddress

- ea: `0x1004683f0`
- end: `0x100468546`
- name: `StartAddress`
- size: `342`
- prototype: `void __stdcall(LPVOID lpFiberParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x10042add0`
- `0x100450cc0`
- `0x1004514c0`
- `0x1004683f0`
- `0x1004bc0a0`
- `0x10051ccf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x100468513`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x100468513`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x10046851d`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x10046851d`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x10046852e`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x10046852e`
- `KERNEL32!GetLastError` at `0x1004684d8`
- `KERNEL32!GetLastError` at `0x1004684d8`
- `KERNEL32!TlsGetValue` at `0x100468416`
- `KERNEL32!TlsGetValue` at `0x100468435`
- `KERNEL32!TlsGetValue` at `0x10046848f`
- `KERNEL32!TlsGetValue` at `0x100468416`
- `KERNEL32!TlsGetValue` at `0x100468435`
- `KERNEL32!TlsGetValue` at `0x10046848f`
- `KERNEL32!SwitchToFiber` at `0x10046853b`
- `KERNEL32!SwitchToFiber` at `0x10046853b`
- `ADVAPI32!SetThreadToken` at `0x1004684ce`
- `ADVAPI32!SetThreadToken` at `0x1004684ce`

## string_xrefs

- `0x1004684e8`: `src\dktemp\sos\include\worker.inl`
- `0x100468406`: `SetThreadToken failed: %d`

## pseudocode

```c
void __fastcall __noreturn StartAddress(LPVOID lpFiberParameter)
{
  _QWORD *Value; // rax
  int v2; // edx
  __int64 v3; // rcx
  __int64 v4; // rdx
  _QWORD *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rdi
  _DWORD *v8; // rbx
  __int64 v9; // rbx
  void *v10; // rdx
  DWORD LastError; // eax

  while ( 1 )
  {
    Value = TlsGetValue(dwTlsIndex);
    if ( !Value || !Value[32] )
    {
      sub_100450CC0(v3, v2);
      Value = TlsGetValue(dwTlsIndex);
    }
    v4 = Value[32];
    v5 = *(_QWORD **)(v4 + 520);
    *(_QWORD *)(v4 + 536) = 0;
    sub_1004BC0A0(v5[644] + 192LL, v4, 2);
    v6 = v5[635];
    v5[634] = v6;
    _InterlockedExchange((volatile __int32 *)(v6 + 640), 2);
    v7 = v5[635];
    v8 = TlsGetValue(dwTlsIndex);
    sub_1004514C0(v8);
    v8[66] &= 0xFFFFFFFC;
    sub_10042ADD0(v8, *(unsigned int *)(v7 + 88));
    v9 = *(_QWORD *)(v7 + 536);
    v10 = *(void **)(v7 + 448);
    if ( *(void **)(v9 + 304) != v10 )
    {
      if ( !SetThreadToken(0, v10) )
      {
        LastError = GetLastError();
        sub_10051CCF0(
          1,
          (unsigned int)"result",
          (unsigned int)"src\\dktemp\\sos\\include\\worker.inl",
          3446,
          "SetThreadToken failed: %d",
          LastError);
      }
      *(_QWORD *)(v9 + 304) = *(_QWORD *)(v7 + 448);
    }
    if ( (clearfp() & 0x10) != 0 )
      fpreset();
    controlfp(*(_DWORD *)(v7 + 720), 0x8001Fu);
    SwitchToFiber(*(LPVOID *)(v7 + 552));
  }
}

```

## disassembly

```asm
0x1004683f0  mov     [rsp+arg_0], rbx
0x1004683f5  mov     [rsp+arg_8], rbp
0x1004683fa  mov     [rsp+arg_10], rsi
0x1004683ff  push    rdi
0x100468400  sub     rsp, 30h
0x100468404  xor     ebp, ebp
0x100468406  lea     rsi, aSetthreadtoken_0; "SetThreadToken failed: %d"
0x10046840d  nop     dword ptr [rax]
0x100468410  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x100468416  call    cs:TlsGetValue
0x10046841c  test    rax, rax
0x10046841f  jz      short loc_10046842A
0x100468421  cmp     [rax+100h], rbp
0x100468428  jnz     short loc_10046843B
0x10046842a  call    sub_100450CC0
0x10046842f  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x100468435  call    cs:TlsGetValue
0x10046843b  mov     rdx, [rax+100h]
0x100468442  mov     r8d, 2
0x100468448  mov     rbx, [rdx+208h]
0x10046844f  mov     [rdx+218h], rbp
0x100468456  mov     rcx, [rbx+1420h]
0x10046845d  add     rcx, 0C0h
0x100468464  call    sub_1004BC0A0
0x100468469  mov     rcx, [rbx+13D8h]
0x100468470  mov     eax, 2
0x100468475  mov     [rbx+13D0h], rcx
0x10046847c  xchg    eax, [rcx+280h]
0x100468482  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x100468488  mov     rdi, [rbx+13D8h]
0x10046848f  call    cs:TlsGetValue
0x100468495  mov     rcx, rax; void *
0x100468498  mov     rdx, rdi
0x10046849b  mov     rbx, rax
0x10046849e  call    sub_1004514C0
0x1004684a3  and     dword ptr [rbx+108h], 0FFFFFFFCh
0x1004684aa  mov     rcx, rbx
0x1004684ad  mov     edx, [rdi+58h]
0x1004684b0  call    sub_10042ADD0
0x1004684b5  mov     rbx, [rdi+218h]
0x1004684bc  mov     rdx, [rdi+1C0h]; Token
0x1004684c3  cmp     [rbx+130h], rdx
0x1004684ca  jz      short loc_100468513
0x1004684cc  xor     ecx, ecx; Thread
0x1004684ce  call    cs:SetThreadToken
0x1004684d4  test    eax, eax
0x1004684d6  jnz     short loc_100468505
0x1004684d8  call    cs:GetLastError
0x1004684de  mov     [rsp+38h+var_10], eax
0x1004684e2  mov     r9d, 0D76h
0x1004684e8  lea     r8, aSrcDktempSosIn_3; "src\\dktemp\\sos\\include\\worker.inl"
0x1004684ef  mov     [rsp+38h+var_18], rsi
0x1004684f4  lea     rdx, aResult; "result"
0x1004684fb  mov     ecx, 1
0x100468500  call    sub_10051CCF0
0x100468505  mov     rax, [rdi+1C0h]
0x10046850c  mov     [rbx+130h], rax
0x100468513  call    cs:_clearfp
0x100468519  test    al, 10h
0x10046851b  jz      short loc_100468523
0x10046851d  call    cs:_fpreset
0x100468523  mov     ecx, [rdi+2D0h]; NewValue
0x100468529  mov     edx, 8001Fh; Mask
0x10046852e  call    cs:_controlfp
0x100468534  mov     rcx, [rdi+228h]; lpFiber
0x10046853b  call    cs:SwitchToFiber
0x100468541  jmp     loc_100468410
```
