# AllocateMultiObjectBuffer

- ea: `0x180013fd4`
- end: `0x18001407c`
- name: `AllocateMultiObjectBuffer`
- size: `168`
- prototype: `__int64 __fastcall(void *, int, __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014320`

## callees

- `0x180004200`
- `0x180005060`
- `0x1800066f0`
- `0x180013fd4`

## string_xrefs

- `0x180014032`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall AllocateMultiObjectBuffer(void *a1, int a2, __int64 *a3, unsigned int *a4)
{
  NTSTATUS Property; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rax
  ULONG pcbResult; // [rsp+30h] [rbp-38h] BYREF
  UCHAR pbOutput[48]; // [rsp+38h] [rbp-30h] BYREF

  *(_QWORD *)pbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(a1, L"MultiObjectLength", pbOutput, 8u, &pcbResult, 0);
  v8 = Property;
  if ( Property >= 0 )
  {
    v11 = *(_DWORD *)pbOutput + a2 * *(_DWORD *)&pbOutput[4];
    v12 = SafeAllocaAllocateFromHeap(v11);
    if ( v12 )
    {
      *a4 = v11;
      v8 = 0;
      *a3 = v12;
      return v8;
    }
    v8 = -1073741801;
    v9 = 1058;
    v10 = 3221225495LL;
  }
  else
  {
    v9 = 1043;
    v10 = (unsigned int)Property;
  }
  DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v9);
  return v8;
}

```

## disassembly

```asm
0x180013fd4  mov     rax, rsp
0x180013fd7  push    rbx
0x180013fd8  push    rbp
0x180013fd9  push    rsi
0x180013fda  push    rdi
0x180013fdb  sub     rsp, 48h
0x180013fdf  mov     dword ptr [rax-40h], 0
0x180013fe6  mov     rdi, r9
0x180013fe9  mov     qword ptr [rax-30h], 0
0x180013ff1  mov     rsi, r8
0x180013ff4  mov     dword ptr [rax-38h], 0
0x180013ffb  lea     rax, [rax-38h]
0x180013fff  mov     ebp, edx
0x180014001  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180014006  mov     r9d, 8; cbOutput
0x18001400c  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x180014011  lea     rdx, aMultiobjectlen; "MultiObjectLength"
0x180014018  call    BCryptGetProperty
0x18001401d  mov     ebx, eax
0x18001401f  test    eax, eax
0x180014021  jns     short loc_180014040
0x180014023  mov     r9d, 413h
0x180014029  mov     ecx, eax
0x18001402b  lea     rdx, aStatus; "Status"
0x180014032  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014039  call    DebugTraceError
0x18001403e  jmp     short loc_180014070
0x180014040  mov     ebx, [rsp+68h+var_2C]
0x180014044  imul    ebx, ebp
0x180014047  add     ebx, dword ptr [rsp+68h+pbOutput]
0x18001404b  mov     ecx, ebx
0x18001404d  call    SafeAllocaAllocateFromHeap
0x180014052  test    rax, rax
0x180014055  jnz     short loc_180014069
0x180014057  mov     ebx, 0C0000017h
0x18001405c  mov     r9d, 422h
0x180014062  mov     ecx, 0C0000017h
0x180014067  jmp     short loc_18001402B
0x180014069  mov     [rdi], ebx
0x18001406b  xor     ebx, ebx
0x18001406d  mov     [rsi], rax
0x180014070  mov     eax, ebx
0x180014072  add     rsp, 48h
0x180014076  pop     rdi
0x180014077  pop     rsi
0x180014078  pop     rbp
0x180014079  pop     rbx
0x18001407a  retn
```
