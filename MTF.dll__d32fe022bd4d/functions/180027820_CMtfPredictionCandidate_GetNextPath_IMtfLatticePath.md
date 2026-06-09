# CMtfPredictionCandidate::GetNextPath(IMtfLatticePath * *)

- ea: `0x180027820`
- end: `0x1800278a4`
- name: `?GetNextPath@CMtfPredictionCandidate@@UEAAJPEAPEAUIMtfLatticePath@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this, struct IMtfLatticePath **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180027820`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::GetNextPath(CMtfPredictionCandidate *this, struct IMtfLatticePath **a2)
{
  __int64 result; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  int (__fastcall ***v5)(_QWORD); // rcx

  if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 3) - *((_QWORD *)this + 2)) >> 3) <= 2 )
  {
    *a2 = 0;
    v3 = *((_QWORD *)this + 2);
    v4 = *((_QWORD *)this + 3) - v3;
    if ( v4 == 16 )
    {
      v5 = *(int (__fastcall ****)(_QWORD))(v3 + 8);
      if ( v5 )
      {
        try
        {
          if ( (**v5)(v5) >= 0 )
            result = 0;
          else
            result = 2147500037LL;
        }
        catch ( ... )
        {
          return 2147500037LL;
        }
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    MEMORY[0] = 0;
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x180027820  sub     rsp, 28h
0x180027824  mov     r8, rdx
0x180027827  mov     rax, [rcx+18h]
0x18002782b  sub     rax, [rcx+10h]
0x18002782f  sar     rax, 3
0x180027833  cmp     rax, 2
0x180027837  jbe     short loc_18002784B
0x180027839  mov     dword ptr ds:0, 0
0x180027844  mov     eax, 8000FFFFh
0x180027849  jmp     short loc_18002789E
0x18002784b  mov     qword ptr [rdx], 0
0x180027852  mov     rdx, [rcx+10h]
0x180027856  mov     rax, [rcx+18h]
0x18002785a  sub     rax, rdx
0x18002785d  cmp     rax, 10h
0x180027861  jz      short loc_18002786A
0x180027863  mov     eax, 1
0x180027868  jmp     short loc_18002789E
0x18002786a  mov     rcx, [rdx+8]
0x18002786e  test    rcx, rcx
0x180027871  jnz     short loc_180027878
0x180027873  lea     eax, [rcx+1]
0x180027876  jmp     short loc_18002789E
0x180027878  mov     rax, [rcx]
0x18002787b  lea     rdx, _GUID_53445657_1e40_40f5_a775_8965c8894c31
0x180027882  mov     rax, [rax]
0x180027885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002788a  test    eax, eax
0x18002788c  jns     short loc_180027895
0x18002788e  mov     eax, 80004005h
0x180027893  jmp     short loc_18002789E
0x180027895  xor     eax, eax
0x180027897  jmp     short loc_18002789E
0x180027899  mov     eax, 80004005h
0x18002789e  add     rsp, 28h
0x1800278a2  retn
```
