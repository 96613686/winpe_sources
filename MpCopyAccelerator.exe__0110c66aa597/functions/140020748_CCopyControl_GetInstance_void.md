# CCopyControl::GetInstance(void)

- ea: `0x140020748`
- end: `0x140020800`
- name: `?GetInstance@CCopyControl@@SAAEAV1@XZ`
- size: `184`
- prototype: `struct CCopyControl *(void)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001e068`
- `0x14001e268`
- `0x14001efa4`
- `0x14001f6a0`
- `0x14001fe80`
- `0x14001ffe0`

## callees

- `0x140005cb8`
- `0x140005d24`
- `0x140005da0`
- `0x140006010`
- `0x140020748`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CCopyControl *CCopyControl::GetInstance(void)
{
  _QWORD *v1; // rax

  if ( dword_14003DC50 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_14003DC50);
    if ( dword_14003DC50 == -1 )
    {
      v1 = operator new(0x18u);
      *v1 = v1;
      v1[1] = v1;
      qword_14003DBF8 = (__int64)v1;
      qword_14003DC08 = 0;
      qword_14003DC10 = 0;
      qword_14003DC18 = 0;
      qword_14003DC20 = 0;
      qword_14003DC28 = 0;
      qword_14003DC30 = 0;
      qword_14003DC38 = 0;
      qword_14003DC40 = 0;
      qword_14003DC48 = 0;
      atexit(CCopyControl::GetInstance_::_2_::_dynamic_atexit_destructor_for__m_Singleton__);
      Init_thread_footer(&dword_14003DC50);
    }
  }
  return (struct CCopyControl *)&qword_14003DBF0;
}

```

## disassembly

```asm
0x140020748  sub     rsp, 28h
0x14002074c  mov     ecx, 4
0x140020751  mov     rax, gs:58h
0x14002075a  mov     rax, [rax]
0x14002075d  mov     eax, [rcx+rax]
0x140020760  cmp     cs:dword_14003DC50, eax
0x140020766  jg      short loc_140020774
0x140020768  lea     rax, qword_14003DBF0
0x14002076f  add     rsp, 28h
0x140020773  retn
0x140020774  lea     rcx, dword_14003DC50
0x14002077b  call    _Init_thread_header
0x140020780  cmp     cs:dword_14003DC50, 0FFFFFFFFh
0x140020787  jnz     short loc_140020768
0x140020789  mov     ecx, 18h; Size
0x14002078e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140020793  mov     [rax], rax
0x140020796  mov     [rax+8], rax
0x14002079a  mov     cs:qword_14003DBF8, rax
0x1400207a1  xor     eax, eax
0x1400207a3  mov     cs:qword_14003DC08, rax
0x1400207aa  mov     cs:qword_14003DC10, rax
0x1400207b1  mov     cs:qword_14003DC18, rax
0x1400207b8  mov     cs:qword_14003DC20, rax
0x1400207bf  mov     cs:qword_14003DC28, rax
0x1400207c6  mov     cs:qword_14003DC30, rax
0x1400207cd  mov     cs:qword_14003DC38, rax
0x1400207d4  mov     cs:qword_14003DC40, rax
0x1400207db  mov     cs:qword_14003DC48, rax
0x1400207e2  lea     rcx, _CCopyControl__GetInstance____2____dynamic_atexit_destructor_for__m_Singleton__; void (__cdecl *)()
0x1400207e9  call    atexit
0x1400207ee  nop
0x1400207ef  lea     rcx, dword_14003DC50
0x1400207f6  call    _Init_thread_footer
0x1400207fb  jmp     loc_140020768
```
