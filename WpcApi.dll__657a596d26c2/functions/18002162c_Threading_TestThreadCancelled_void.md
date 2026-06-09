# Threading::TestThreadCancelled(void)

- ea: `0x18002162c`
- end: `0x1800216c6`
- name: `?TestThreadCancelled@Threading@@YAXXZ`
- size: `154`
- prototype: `void __fastcall(Threading *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800238ec`

## callees

- `0x180003d20`
- `0x18000b274`
- `0x1800210e8`
- `0x18002162c`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180021636`
- `KERNEL32!TlsGetValue` at `0x180021647`
- `KERNEL32!TlsGetValue` at `0x180021657`
- `KERNEL32!TlsGetValue` at `0x180021636`
- `KERNEL32!TlsGetValue` at `0x180021647`
- `KERNEL32!TlsGetValue` at `0x180021657`

## pseudocode

```c
void __fastcall Threading::TestThreadCancelled(Threading *this)
{
  _OWORD pExceptionObject[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v2; // [rsp+40h] [rbp-18h]

  if ( TlsGetValue(dword_18004A6D8)
    && (int)TlsGetValue(dwTlsIndex) <= 0
    && *((_BYTE *)TlsGetValue(dword_18004A6D8) + 12) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_8f71bf2a86f63c0585a15c2236b3f2b4_Traceguids);
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v2 = 0;
    ThreadCancelledException::ThreadCancelledException((ThreadCancelledException *)pExceptionObject);
    throw (ThreadCancelledException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002162c  sub     rsp, 58h
0x180021630  mov     ecx, cs:dword_18004A6D8; dwTlsIndex
0x180021636  call    cs:__imp_TlsGetValue
0x18002163c  test    rax, rax
0x18002163f  jz      short loc_180021663
0x180021641  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180021647  call    cs:__imp_TlsGetValue
0x18002164d  test    eax, eax
0x18002164f  jg      short loc_180021663
0x180021651  mov     ecx, cs:dword_18004A6D8; dwTlsIndex
0x180021657  call    cs:__imp_TlsGetValue
0x18002165d  cmp     byte ptr [rax+0Ch], 0
0x180021661  jnz     short loc_180021668
0x180021663  add     rsp, 58h
0x180021667  retn
0x180021668  mov     rcx, cs:WPP_GLOBAL_Control
0x18002166f  lea     rax, WPP_GLOBAL_Control
0x180021676  cmp     rcx, rax
0x180021679  jz      short loc_180021696
0x18002167b  test    byte ptr [rcx+1Ch], 1
0x18002167f  jz      short loc_180021696
0x180021681  mov     rcx, [rcx+10h]
0x180021685  lea     r8, WPP_8f71bf2a86f63c0585a15c2236b3f2b4_Traceguids
0x18002168c  mov     edx, 15h
0x180021691  call    WPP_SF_
0x180021696  xorps   xmm0, xmm0
0x180021699  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18002169e  xor     eax, eax
0x1800216a0  movups  [rsp+58h+pExceptionObject], xmm0
0x1800216a5  mov     [rsp+58h+var_18], rax
0x1800216aa  movups  [rsp+58h+var_28], xmm0
0x1800216af  call    ??0ThreadCancelledException@@QEAA@XZ; ThreadCancelledException::ThreadCancelledException(void)
0x1800216b4  lea     rdx, _TI4?AVThreadCancelledException@@; pThrowInfo
0x1800216bb  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800216c0  call    _CxxThrowException_0
```
