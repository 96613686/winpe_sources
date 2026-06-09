# Kerb3961::RandomBuffer(unsigned __int64)

- ea: `0x180005e34`
- end: `0x180005efe`
- name: `?RandomBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z`
- size: `202`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005f10`
- `0x180007710`
- `0x180008fa0`
- `0x1800103c0`

## callees

- `0x180001818`
- `0x180005e34`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`

## import_xrefs

- `cng!BCryptGenRandom` at `0x180005ea2`
- `cng!BCryptGenRandom` at `0x180005ea2`

## pseudocode

```c
__int64 __fastcall Kerb3961::RandomBuffer(__int64 a1, const struct std::nothrow_t *a2)
{
  const char *v4; // rdx
  PUCHAR v5; // rsi
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  PUCHAR pbBuffer; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
  {
    utl::make_unique<unsigned char [0],0>(&pbBuffer, a2);
    v5 = pbBuffer;
    if ( pbBuffer )
    {
      v6 = BCryptGenRandom(0, pbBuffer, (ULONG)a2, 2u);
      v7 = v6;
      if ( v6 >= 0 )
      {
        *(_QWORD *)a1 = a2;
        *(_QWORD *)(a1 + 8) = v5;
        *(_DWORD *)(a1 + 16) = 0;
        return a1;
      }
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"RandomFill({bytes, &result[0]})",
        (const char *)(unsigned int)v6);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = v7;
    }
    else
    {
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"result", v4);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = -1073741801;
    }
    if ( v5 )
      Kerb3961Free(v5);
  }
  else
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180005e34  push    rbx
0x180005e36  push    rbp
0x180005e37  push    rsi
0x180005e38  push    rdi
0x180005e39  sub     rsp, 28h
0x180005e3d  mov     rbp, rdx
0x180005e40  mov     rdi, rcx
0x180005e43  test    rdx, rdx
0x180005e46  jnz     short loc_180005E57
0x180005e48  mov     [rcx], rdx
0x180005e4b  mov     [rcx+8], rdx
0x180005e4f  mov     [rcx+10h], edx
0x180005e52  jmp     loc_180005EF1
0x180005e57  lea     rcx, [rsp+48h+pbBuffer]
0x180005e5c  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180005e61  mov     rsi, [rsp+48h+pbBuffer]
0x180005e66  test    rsi, rsi
0x180005e69  setnz   al
0x180005e6c  test    al, al
0x180005e6e  jnz     short loc_180005E94
0x180005e70  lea     rcx, aResult; "result"
0x180005e77  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005e7c  mov     qword ptr [rdi], 0
0x180005e83  mov     qword ptr [rdi+8], 0
0x180005e8b  mov     dword ptr [rdi+10h], 0C0000017h
0x180005e92  jmp     short loc_180005ED4
0x180005e94  mov     r9d, 2; dwFlags
0x180005e9a  mov     r8d, ebp; cbBuffer
0x180005e9d  mov     rdx, rsi; pbBuffer
0x180005ea0  xor     ecx, ecx; hAlgorithm
0x180005ea2  call    cs:__imp_BCryptGenRandom
0x180005ea9  nop     dword ptr [rax+rax+00h]
0x180005eae  mov     ebx, eax
0x180005eb0  test    eax, eax
0x180005eb2  jns     short loc_180005EE3
0x180005eb4  mov     edx, eax; char *
0x180005eb6  lea     rcx, aRandomfillByte; "RandomFill({bytes, &result[0]})"
0x180005ebd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005ec2  mov     qword ptr [rdi], 0
0x180005ec9  mov     qword ptr [rdi+8], 0
0x180005ed1  mov     [rdi+10h], ebx
0x180005ed4  test    rsi, rsi
0x180005ed7  jz      short loc_180005EF1
0x180005ed9  mov     rcx, rsi
0x180005edc  call    Kerb3961Free
0x180005ee1  jmp     short loc_180005EF1
0x180005ee3  mov     [rdi], rbp
0x180005ee6  mov     [rdi+8], rsi
0x180005eea  mov     dword ptr [rdi+10h], 0
0x180005ef1  mov     rax, rdi
0x180005ef4  add     rsp, 28h
0x180005ef8  pop     rdi
0x180005ef9  pop     rsi
0x180005efa  pop     rbp
0x180005efb  pop     rbx
0x180005efc  retn
```
