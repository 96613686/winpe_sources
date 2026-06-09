# VprocessGlobals::acquireFPGlobalCriticalSection(void)

- ea: `0x1800962c0`
- end: `0x1800963a3`
- name: `?acquireFPGlobalCriticalSection@VprocessGlobals@@SAXXZ`
- size: `227`
- prototype: `void(void)`
- caller_count: `45`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ecac`
- `0x18000ff80`
- `0x1800192b0`
- `0x1800498e0`
- `0x18006c2a0`
- `0x180096770`
- `0x180096900`
- `0x180096bb0`
- `0x180096c10`
- `0x180096c80`
- `0x180096cd0`
- `0x180096d20`
- `0x180097024`
- `0x180097280`
- `0x180097480`
- `0x1800975d0`
- `0x1800984e0`
- `0x180098778`
- `0x180098ca0`
- `0x180099590`
- `0x180099e98`
- `0x18009a118`
- `0x18009a6cc`
- `0x18009aae0`
- `0x18009afa0`
- `0x18009b2a0`
- `0x18009ba30`
- `0x18009bfd8`
- `0x1800a1764`
- `0x1800b81f0`
- `0x1800ba000`
- `0x1800c3aa8`
- `0x1800d7130`
- `0x1800db260`
- `0x1800dc2b0`
- `0x1800e1ce0`
- `0x1800ee660`
- `0x1800f2c00`
- `0x1800f6c40`
- `0x1800fd780`
- `0x180101dc0`
- `0x1801239ec`
- `0x180130930`
- `0x180140854`
- `0x180141220`

## callees

- `0x180083790`
- `0x1800961f4`
- `0x1800962c0`
- `0x1800b93d0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180096312`
- `KERNEL32!WaitForSingleObject` at `0x180096312`
- `KERNEL32!TlsGetValue` at `0x180096365`
- `KERNEL32!TlsGetValue` at `0x180096365`
- `KERNEL32!GetCurrentThreadId` at `0x1800962d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800962d9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180096337`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180096337`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void VprocessGlobals::acquireFPGlobalCriticalSection(void)
{
  DWORD CurrentThreadId; // eax
  int v1; // ebx
  VgenericStatus *v2; // rax
  VgenericStatus *v3; // rdi
  LPVOID Value; // rax

  CurrentThreadId = GetCurrentThreadId();
  v1 = CurrentThreadId;
  if ( word_1802B00B8 > 0 && dword_1802AF4A4 == CurrentThreadId )
  {
    ++word_1802B00B8;
  }
  else
  {
    if ( WaitForSingleObject(hEvent, 0x7530u) )
    {
      sub_1800961F4();
      if ( dword_1802B0018 )
        v2 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
      else
        v2 = (VgenericStatus *)malloc(0x20u);
      if ( v2 )
        v3 = VgenericStatus::VgenericStatus(v2, 0x50018u, 0);
      else
        v3 = 0;
      Value = TlsGetValue(dwTlsIndex);
      if ( Value )
        (*(void (__fastcall **)(LPVOID, VgenericStatus *))(*(_QWORD *)Value + 40LL))(Value, v3);
    }
    dword_1802AF4A4 = v1;
    ++word_1802B00B8;
  }
}

```

## disassembly

```asm
0x1800962c0  push    rdi
0x1800962c2  sub     rsp, 30h
0x1800962c6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800962cf  mov     [rsp+38h+arg_8], rbx
0x1800962d4  mov     [rsp+38h+arg_10], rsi
0x1800962d9  call    cs:GetCurrentThreadId
0x1800962df  mov     ebx, eax
0x1800962e1  movzx   ecx, cs:word_1802B00B8
0x1800962e8  xor     esi, esi
0x1800962ea  test    cx, cx
0x1800962ed  jle     short loc_180096306
0x1800962ef  cmp     cs:dword_1802AF4A4, eax
0x1800962f5  jnz     short loc_180096306
0x1800962f7  inc     cx
0x1800962fa  mov     cs:word_1802B00B8, cx
0x180096301  jmp     loc_180096393
0x180096306  mov     edx, 7530h; dwMilliseconds
0x18009630b  mov     rcx, cs:hEvent; hHandle
0x180096312  call    cs:WaitForSingleObject
0x180096318  test    eax, eax
0x18009631a  jz      short loc_180096386
0x18009631c  mov     ecx, eax
0x18009631e  call    sub_1800961F4
0x180096323  mov     ecx, 20h ; ' '; unsigned __int64
0x180096328  cmp     cs:dword_1802B0018, esi
0x18009632e  jz      short loc_180096337
0x180096330  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x180096335  jmp     short loc_18009633D
0x180096337  call    cs:malloc
0x18009633d  mov     [rsp+38h+arg_0], rax
0x180096342  test    rax, rax
0x180096345  jz      short loc_18009635C
0x180096347  xor     r8d, r8d; int
0x18009634a  mov     edx, 50018h; unsigned int
0x18009634f  mov     rcx, rax; this
0x180096352  call    ??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x180096357  mov     rdi, rax
0x18009635a  jmp     short loc_18009635F
0x18009635c  mov     rdi, rsi
0x18009635f  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180096365  call    cs:TlsGetValue
0x18009636b  mov     r8, rax
0x18009636e  test    rax, rax
0x180096371  jz      short loc_180096386
0x180096373  mov     rcx, [rax]
0x180096376  mov     rax, [rcx+28h]
0x18009637a  mov     rdx, rdi
0x18009637d  mov     rcx, r8
0x180096380  call    cs:__guard_dispatch_icall_fptr
0x180096386  mov     cs:dword_1802AF4A4, ebx
0x18009638c  inc     cs:word_1802B00B8
0x180096393  mov     rbx, [rsp+38h+arg_8]
0x180096398  mov     rsi, [rsp+38h+arg_10]
0x18009639d  add     rsp, 30h
0x1800963a1  pop     rdi
0x1800963a2  retn
```
