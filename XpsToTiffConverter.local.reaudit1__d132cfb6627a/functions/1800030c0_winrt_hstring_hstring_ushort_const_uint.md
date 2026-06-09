# winrt::hstring::hstring(ushort const *,uint)

- ea: `0x1800030c0`
- end: `0x180003181`
- name: `??0hstring@winrt@@QEAA@PEBGI@Z`
- size: `193`
- prototype: `_QWORD(winrt::hstring *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180008934`
- `0x1800096f0`
- `0x18000a270`
- `0x18000c920`

## callees

- `0x1800020f0`
- `0x180002168`
- `0x180002174`
- `0x180003060`
- `0x1800030c0`
- `0x1800031cc`
- `0x180008f08`

## pseudocode

```c
winrt::hstring *__fastcall winrt::hstring::hstring(winrt::hstring *this, const char *a2, unsigned int a3)
{
  __int64 v3; // rsi
  char *v6; // rbx
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = a3;
  if ( a3 )
  {
    if ( 2 * (unsigned __int64)a3 + 32 > 0xFFFFFFFF )
    {
      std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, a2);
      throw (std::invalid_argument *)pExceptionObject;
    }
    ProcessHeap = WINRT_IMPL_GetProcessHeap();
    v8 = (char *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, 2 * v3 + 32);
    v6 = v8;
    if ( !v8 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
    *(_DWORD *)v8 = 0;
    *((_QWORD *)v8 + 2) = v8 + 28;
    *((_DWORD *)v8 + 1) = v3;
    _InterlockedExchange((volatile __int32 *)v8 + 6, 1);
    *(_WORD *)&v8[2 * v3 + 28] = 0;
    memcpy_s(v8 + 28, 2 * v3, a2, 2 * v3);
  }
  else
  {
    v6 = 0;
  }
  *(_QWORD *)this = v6;
  return this;
}

```

## disassembly

```asm
0x1800030c0  push    rbx
0x1800030c2  push    rbp
0x1800030c3  push    rsi
0x1800030c4  push    rdi
0x1800030c5  push    r14
0x1800030c7  sub     rsp, 40h
0x1800030cb  mov     esi, r8d
0x1800030ce  mov     rbp, rdx
0x1800030d1  mov     rdi, rcx
0x1800030d4  test    r8d, r8d
0x1800030d7  jnz     short loc_1800030DD
0x1800030d9  xor     ebx, ebx
0x1800030db  jmp     short loc_180003138
0x1800030dd  lea     rbx, ds:20h[rsi*2]
0x1800030e5  mov     eax, 0FFFFFFFFh
0x1800030ea  cmp     rbx, rax
0x1800030ed  ja      short loc_180003165
0x1800030ef  call    WINRT_IMPL_GetProcessHeap
0x1800030f4  mov     rcx, rax; hHeap
0x1800030f7  mov     r8, rbx; dwBytes
0x1800030fa  xor     edx, edx; dwFlags
0x1800030fc  call    WINRT_IMPL_HeapAlloc
0x180003101  mov     rbx, rax
0x180003104  test    rax, rax
0x180003107  jz      short loc_180003149
0x180003109  lea     rcx, [rax+1Ch]; Destination
0x18000310d  mov     dword ptr [rax], 0
0x180003113  mov     [rax+10h], rcx
0x180003117  xor     edx, edx
0x180003119  mov     [rax+4], esi
0x18000311c  mov     r8, rbp; Source
0x18000311f  mov     eax, 1
0x180003124  xchg    eax, [rbx+18h]
0x180003127  mov     [rbx+rsi*2+1Ch], dx
0x18000312c  lea     rdx, [rsi+rsi]; DestinationSize
0x180003130  mov     r9, rdx; SourceSize
0x180003133  call    memcpy_s
0x180003138  mov     [rdi], rbx
0x18000313b  mov     rax, rdi
0x18000313e  add     rsp, 40h
0x180003142  pop     r14
0x180003144  pop     rdi
0x180003145  pop     rsi
0x180003146  pop     rbp
0x180003147  pop     rbx
0x180003148  retn
0x180003149  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000314e  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180003153  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000315a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000315f  call    _CxxThrowException_0
0x180003165  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000316a  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18000316f  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180003176  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000317b  call    _CxxThrowException_0
```
