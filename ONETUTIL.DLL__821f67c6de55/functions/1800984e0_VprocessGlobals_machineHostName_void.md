# VprocessGlobals::machineHostName(void)

- ea: `0x1800984e0`
- end: `0x18009871b`
- name: `?machineHostName@VprocessGlobals@@SAAEBVVstring@@XZ`
- size: `571`
- prototype: `const struct Vstring *(void)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180040b90`
- `0x180040c10`
- `0x180049170`
- `0x180083790`
- `0x1800838f0`
- `0x180083b70`
- `0x180083bb0`
- `0x180083bf0`
- `0x1800962c0`
- `0x180098320`
- `0x1800984e0`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800986d2`
- `KERNEL32!SetEvent` at `0x1800986d2`
- `KERNEL32!GetComputerNameExW` at `0x1800985d6`
- `KERNEL32!GetComputerNameExW` at `0x1800985d6`
- `KERNEL32!TlsGetValue` at `0x180098547`
- `KERNEL32!TlsGetValue` at `0x18009855c`
- `KERNEL32!TlsGetValue` at `0x180098547`
- `KERNEL32!TlsGetValue` at `0x18009855c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800986bb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800986bb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009857f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009863f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009857f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18009863f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
const struct Vstring *VprocessGlobals::machineHostName(void)
{
  LPVOID Value; // rbx
  char *v1; // rax
  struct Vstatus *v2; // rax
  char *v3; // rax
  Vstring *v4; // rax
  char *v5; // rcx
  DWORD nSize[2]; // [rsp+28h] [rbp-E0h] BYREF
  char *v8[3]; // [rsp+30h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+48h] [rbp-C0h] BYREF

  v8[1] = (char *)-2LL;
  if ( qword_1802AF430 )
    return (const struct Vstring *)qword_1802AF430;
  VprocessGlobals::acquireFPGlobalCriticalSection();
  if ( !qword_1802AF430 && TlsGetValue(dwTlsIndex) )
  {
    Value = TlsGetValue(dwTlsIndex);
    if ( !*((_QWORD *)Value + 14) )
    {
      if ( dword_1802B0018 )
        v1 = (char *)COWSAllocator::AllocCurrentHeap(1u);
      else
        v1 = (char *)malloc(1u);
      v8[0] = v1;
      if ( v1 )
        *v1 = 0;
      else
        v1 = 0;
      *((_QWORD *)Value + 14) = v1;
    }
    v2 = Vdns::init(*((Vdns **)Value + 14));
    if ( v2 )
    {
      (**(void (__fastcall ***)(struct Vstatus *, __int64))v2)(v2, 1);
    }
    else
    {
      nSize[1] = 261;
      if ( GetComputerNameExW(ComputerNameDnsHostname, Buffer, &nSize[1]) )
      {
        Buffer[260] = 0;
        Vstring::Vstring((Vstring *)v8, Buffer);
        if ( dword_1802B0018 )
        {
          LOBYTE(nSize[0]) = COWSAllocator::IsCurrentHeapLocal();
          BYTE1(nSize[0]) = LOBYTE(nSize[0]) == 1;
          if ( LOBYTE(nSize[0]) == 1 )
            COWSAllocator::UseGlobalHeap();
        }
        if ( dword_1802B0018 )
          v3 = (char *)COWSAllocator::AllocCurrentHeap(8u);
        else
          v3 = (char *)malloc(8u);
        v8[2] = v3;
        if ( v3 )
          v4 = Vstring::Vstring((Vstring *)v3, v8[0]);
        else
          v4 = 0;
        _InterlockedExchange64(&qword_1802AF430, (__int64)v4);
        if ( dword_1802B0018 && BYTE1(nSize[0]) )
        {
          if ( LOBYTE(nSize[0]) )
            COWSAllocator::UseLocalHeap();
          else
            COWSAllocator::UseGlobalHeap();
        }
        v5 = v8[0] - 12;
        if ( !_InterlockedDecrement((volatile signed __int32 *)v8[0] - 3) && v5 != (char *)&dword_1802AFD50 )
        {
          if ( dword_1802B0018 )
            COWSAllocator::Free(v5);
          else
            free(v5);
        }
      }
    }
  }
  if ( !--word_1802B00B8 )
    SetEvent(hEvent);
  if ( qword_1802AF430 )
    return (const struct Vstring *)qword_1802AF430;
  else
    return (const struct Vstring *)sub_180098320();
}

```

## disassembly

```asm
0x1800984e0  mov     rax, rsp
0x1800984e3  push    rbp
0x1800984e4  lea     rbp, [rax-168h]
0x1800984eb  sub     rsp, 260h
0x1800984f2  mov     [rsp+260h+var_230], 0FFFFFFFFFFFFFFFEh
0x1800984fb  mov     [rax+8], rbx
0x1800984ff  mov     [rax+10h], rsi
0x180098503  mov     [rax+18h], rdi
0x180098507  mov     [rax+20h], r14
0x18009850b  mov     rax, cs:__security_cookie
0x180098512  xor     rax, rsp
0x180098515  mov     [rbp+160h+var_10], rax
0x18009851c  xor     edi, edi
0x18009851e  cmp     cs:qword_1802AF430, rdi
0x180098525  jnz     loc_1800986E8
0x18009852b  call    ?acquireFPGlobalCriticalSection@VprocessGlobals@@SAXXZ; VprocessGlobals::acquireFPGlobalCriticalSection(void)
0x180098530  or      r14d, 0FFFFFFFFh
0x180098534  cmp     cs:qword_1802AF430, rdi
0x18009853b  jnz     loc_1800986C1
0x180098541  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180098547  call    cs:TlsGetValue
0x18009854d  test    rax, rax
0x180098550  jz      loc_1800986C1
0x180098556  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18009855c  call    cs:TlsGetValue
0x180098562  mov     rbx, rax
0x180098565  lea     esi, [rdi+1]
0x180098568  cmp     [rax+70h], rdi
0x18009856c  jnz     short loc_18009859B
0x18009856e  mov     ecx, esi; unsigned __int64
0x180098570  cmp     cs:dword_1802B0018, edi
0x180098576  jz      short loc_18009857F
0x180098578  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18009857d  jmp     short loc_180098585
0x18009857f  call    cs:malloc
0x180098585  mov     [rsp+260h+var_238], rax
0x18009858a  test    rax, rax
0x18009858d  jz      short loc_180098594
0x18009858f  mov     [rax], dil
0x180098592  jmp     short loc_180098597
0x180098594  mov     rax, rdi
0x180098597  mov     [rbx+70h], rax
0x18009859b  mov     rcx, [rbx+70h]; this
0x18009859f  call    ?init@Vdns@@QEAAPEAVVstatus@@XZ; Vdns::init(void)
0x1800985a4  mov     r8, rax
0x1800985a7  test    rax, rax
0x1800985aa  jz      short loc_1800985C2
0x1800985ac  mov     rcx, [rax]
0x1800985af  mov     rax, [rcx]
0x1800985b2  mov     edx, esi
0x1800985b4  mov     rcx, r8
0x1800985b7  call    cs:__guard_dispatch_icall_fptr
0x1800985bd  jmp     loc_1800986C1
0x1800985c2  mov     [rsp+260h+nSize+4], 105h
0x1800985ca  lea     r8, [rsp+260h+nSize+4]; nSize
0x1800985cf  lea     rdx, [rsp+260h+Buffer]; lpBuffer
0x1800985d4  mov     ecx, esi; NameType
0x1800985d6  call    cs:GetComputerNameExW
0x1800985dc  test    eax, eax
0x1800985de  jz      loc_1800986C1
0x1800985e4  mov     [rbp+160h+var_18], di
0x1800985eb  lea     rdx, [rsp+260h+Buffer]; wchar_t *
0x1800985f0  lea     rcx, [rsp+260h+var_238]; this
0x1800985f5  call    ??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x1800985fa  nop
0x1800985fb  cmp     cs:dword_1802B0018, edi
0x180098601  jz      short loc_18009862B
0x180098603  call    ?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x180098608  mov     byte ptr [rsp+260h+nSize], al
0x18009860c  cmp     al, sil
0x18009860f  setz    cl
0x180098612  mov     byte ptr [rsp+260h+nSize+1], cl
0x180098616  test    cl, cl
0x180098618  jz      short loc_18009862B
0x18009861a  test    al, al
0x18009861c  jz      short loc_180098625
0x18009861e  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x180098623  jmp     short loc_18009862B
0x180098625  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x18009862a  nop
0x18009862b  mov     ecx, 8; unsigned __int64
0x180098630  cmp     cs:dword_1802B0018, edi
0x180098636  jz      short loc_18009863F
0x180098638  call    ?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18009863d  jmp     short loc_180098645
0x18009863f  call    cs:malloc
0x180098645  mov     qword ptr [rsp+260h+var_228], rax
0x18009864a  test    rax, rax
0x18009864d  jz      short loc_18009865E
0x18009864f  mov     rdx, [rsp+260h+var_238]; char *
0x180098654  mov     rcx, rax; this
0x180098657  call    ??0Vstring@@QEAA@PEBD@Z; Vstring::Vstring(char const *)
0x18009865c  jmp     short loc_180098661
0x18009865e  mov     rax, rdi
0x180098661  xchg    rax, cs:qword_1802AF430
0x180098668  cmp     cs:dword_1802B0018, edi
0x18009866e  jz      short loc_18009868B
0x180098670  cmp     byte ptr [rsp+260h+nSize+1], dil
0x180098675  jz      short loc_18009868B
0x180098677  cmp     byte ptr [rsp+260h+nSize], dil
0x18009867c  jz      short loc_180098685
0x18009867e  call    ?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180098683  jmp     short loc_18009868B
0x180098685  call    ?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x18009868a  nop
0x18009868b  mov     rcx, [rsp+260h+var_238]
0x180098690  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x180098694  mov     eax, r14d
0x180098697  lock xadd [rcx], eax
0x18009869b  add     eax, r14d
0x18009869e  jnz     short loc_1800986C1
0x1800986a0  lea     rax, dword_1802AFD50
0x1800986a7  cmp     rcx, rax
0x1800986aa  jz      short loc_1800986C1
0x1800986ac  cmp     cs:dword_1802B0018, edi
0x1800986b2  jz      short loc_1800986BB
0x1800986b4  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1800986b9  jmp     short loc_1800986C1
0x1800986bb  call    cs:free
0x1800986c1  add     cs:word_1802B00B8, r14w
0x1800986c9  jnz     short loc_1800986D8
0x1800986cb  mov     rcx, cs:hEvent; hEvent
0x1800986d2  call    cs:SetEvent
0x1800986d8  cmp     cs:qword_1802AF430, rdi
0x1800986df  jnz     short loc_1800986E8
0x1800986e1  call    sub_180098320
0x1800986e6  jmp     short loc_1800986EF
0x1800986e8  mov     rax, cs:qword_1802AF430
0x1800986ef  mov     rcx, [rbp+160h+var_10]
0x1800986f6  xor     rcx, rsp
0x1800986f9  call    sub_1801503E0
0x1800986fe  lea     r11, [rsp+260h+var_s0]
0x180098706  mov     rbx, [r11+10h]
0x18009870a  mov     rsi, [r11+18h]
0x18009870e  mov     rdi, [r11+20h]
0x180098712  mov     r14, [r11+28h]
0x180098716  mov     rsp, r11
0x180098719  pop     rbp
0x18009871a  retn
```
