# CAACDec::WriteRawAACFrame(uchar const *,ulong)

- ea: `0x180001740`
- end: `0x1800018c7`
- name: `?WriteRawAACFrame@CAACDec@@IEAAJPEBEK@Z`
- size: `391`
- prototype: `__int64 __fastcall(CAACDec *this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180002550`

## callees

- `0x180001740`
- `0x180003af0`
- `0x18003daf0`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800017f0`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800017f0`

## string_xrefs

- `0x180001771`: `CAACDec::WriteRawAACFrame`
- `0x180001809`: `CAACDec::WriteRawAACFrame`
- `0x180001848`: `CAACDec::WriteRawAACFrame`
- `0x180001892`: `CAACDec::WriteRawAACFrame`
- `0x180001758`: `CAACDec::WriteRawAACFrame(dwInBufferSize=%d, pInBuffer=0x%p) Enter`
- `0x18000186b`: `CAACDec::WriteRawAACFrame() m_ulOutputFrameCnt=%d, m_ulBadFrameCnt=%d)`
- `0x180001822`: `CAACDec::WriteRawAACFrame() m_TimePerFrame = %12I64d, updated m_hnsOutputSampleDuration = %12I64d`

## pseudocode

```c
__int64 __fastcall CAACDec::WriteRawAACFrame(CAACDec *this, const unsigned __int8 *a2, unsigned int a3)
{
  TraceLoggingHelperBase *v3; // rsi
  int v7; // edi
  int v8; // r8d
  int v9; // eax

  v3 = (CAACDec *)((char *)this + 246488);
  TraceLoggingHelperBase::TraceVA(
    (CAACDec *)((char *)this + 246488),
    5u,
    "CAACDec::WriteRawAACFrame",
    0x206u,
    "CAACDec::WriteRawAACFrame(dwInBufferSize=%d, pInBuffer=0x%p) Enter",
    a3,
    a2);
  if ( a3 - 1 > 0xBFFF )
  {
    v7 = -2147467259;
  }
  else
  {
    *((_DWORD *)this + 28) = a3;
    memcpy_s_0((char *)this + 132, 0xC000u, a2, a3);
    v7 = (*(__int64 (__fastcall **)(CAACDec *, _QWORD))(*(_QWORD *)this + 24LL))(this, *((unsigned int *)this + 28));
    if ( v7 >= 0 )
    {
      v8 = *((_DWORD *)this + 61475);
      ++*((_DWORD *)this + 61503);
      ++*((_DWORD *)this + 61504);
      *((_DWORD *)this + 29) = 1024;
      *((_DWORD *)this + 61487) = v8;
      v9 = MulDiv(1024, 10000000, v8);
      *((_QWORD *)this + 4) = v9;
      *((_QWORD *)this + 8) += v9;
      TraceLoggingHelperBase::TraceVA(
        v3,
        5u,
        "CAACDec::WriteRawAACFrame",
        0x224u,
        "CAACDec::WriteRawAACFrame() m_TimePerFrame = %12I64d, updated m_hnsOutputSampleDuration = %12I64d",
        v9,
        *((_QWORD *)this + 8));
    }
  }
  TraceLoggingHelperBase::TraceVA(
    v3,
    5u,
    "CAACDec::WriteRawAACFrame",
    0x228u,
    "CAACDec::WriteRawAACFrame() m_ulOutputFrameCnt=%d, m_ulBadFrameCnt=%d)",
    *((_DWORD *)this + 61504),
    *((_DWORD *)this + 61505));
  if ( v7 )
    TraceLoggingHelperBase::TraceVA(
      v3,
      2u,
      "CAACDec::WriteRawAACFrame",
      0x229u,
      "Error %08X returned: File: %s, Line: %d",
      v7,
      "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdecxheaac.cpp",
      553);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180001740  push    rbx
0x180001742  push    rbp
0x180001743  push    rsi
0x180001744  push    rdi
0x180001745  sub     rsp, 48h
0x180001749  mov     [rsp+68h+var_38], rdx
0x18000174e  lea     rsi, [rcx+3C2D8h]
0x180001755  mov     edi, r8d
0x180001758  lea     rax, aCaacdecWritera_0; "CAACDec::WriteRawAACFrame(dwInBufferSiz"...
0x18000175f  mov     rbp, rdx
0x180001762  mov     dword ptr [rsp+68h+var_40], edi
0x180001766  mov     rbx, rcx
0x180001769  mov     [rsp+68h+Format], rax; Format
0x18000176e  mov     rcx, rsi; this
0x180001771  lea     r8, aCaacdecWritera; "CAACDec::WriteRawAACFrame"
0x180001778  mov     r9d, 206h; unsigned int
0x18000177e  mov     edx, 5; unsigned __int8
0x180001783  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180001788  lea     eax, [rdi-1]
0x18000178b  cmp     eax, 0BFFFh
0x180001790  ja      loc_18000183D
0x180001796  mov     r9d, edi; SourceSize
0x180001799  mov     [rbx+70h], edi
0x18000179c  lea     rcx, [rbx+84h]; Destination
0x1800017a3  mov     r8, rbp; Source
0x1800017a6  mov     edx, 0C000h; DestinationSize
0x1800017ab  call    memcpy_s_0
0x1800017b0  mov     rax, [rbx]
0x1800017b3  mov     rcx, rbx
0x1800017b6  mov     edx, [rbx+70h]
0x1800017b9  mov     rax, [rax+18h]
0x1800017bd  call    cs:__guard_dispatch_icall_fptr
0x1800017c3  mov     edi, eax
0x1800017c5  test    eax, eax
0x1800017c7  js      short loc_180001842
0x1800017c9  mov     r8d, [rbx+3C08Ch]; nDenominator
0x1800017d0  mov     ecx, 400h; nNumber
0x1800017d5  inc     dword ptr [rbx+3C0FCh]
0x1800017db  mov     edx, 989680h; nNumerator
0x1800017e0  inc     dword ptr [rbx+3C100h]
0x1800017e6  mov     [rbx+74h], ecx
0x1800017e9  mov     [rbx+3C0BCh], r8d
0x1800017f0  call    cs:__imp_MulDiv
0x1800017f7  nop     dword ptr [rax+rax+00h]
0x1800017fc  movsxd  rcx, eax
0x1800017ff  mov     r9d, 224h; unsigned int
0x180001805  mov     [rbx+20h], rcx
0x180001809  lea     r8, aCaacdecWritera; "CAACDec::WriteRawAACFrame"
0x180001810  add     [rbx+40h], rcx
0x180001814  mov     edx, 5; unsigned __int8
0x180001819  mov     rax, [rbx+40h]
0x18000181d  mov     [rsp+68h+var_38], rax
0x180001822  lea     rax, aCaacdecWritera_2; "CAACDec::WriteRawAACFrame() m_TimePerFr"...
0x180001829  mov     [rsp+68h+var_40], rcx
0x18000182e  mov     rcx, rsi; this
0x180001831  mov     [rsp+68h+Format], rax; Format
0x180001836  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18000183b  jmp     short loc_180001842
0x18000183d  mov     edi, 80004005h
0x180001842  mov     eax, [rbx+3C104h]
0x180001848  lea     r8, aCaacdecWritera; "CAACDec::WriteRawAACFrame"
0x18000184f  mov     dword ptr [rsp+68h+var_38], eax
0x180001853  mov     r9d, 228h; unsigned int
0x180001859  mov     eax, [rbx+3C100h]
0x18000185f  mov     edx, 5; unsigned __int8
0x180001864  mov     dword ptr [rsp+68h+var_40], eax
0x180001868  mov     rcx, rsi; this
0x18000186b  lea     rax, aCaacdecWritera_1; "CAACDec::WriteRawAACFrame() m_ulOutputF"...
0x180001872  mov     [rsp+68h+Format], rax; Format
0x180001877  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18000187c  test    edi, edi
0x18000187e  jz      short loc_1800018BB
0x180001880  mov     r9d, 229h; unsigned int
0x180001886  lea     rax, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\aacdec\\curren"...
0x18000188d  mov     [rsp+68h+var_30], r9d
0x180001892  lea     r8, aCaacdecWritera; "CAACDec::WriteRawAACFrame"
0x180001899  mov     [rsp+68h+var_38], rax
0x18000189e  mov     edx, 2; unsigned __int8
0x1800018a3  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x1800018aa  mov     dword ptr [rsp+68h+var_40], edi
0x1800018ae  mov     rcx, rsi; this
0x1800018b1  mov     [rsp+68h+Format], rax; Format
0x1800018b6  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800018bb  mov     eax, edi
0x1800018bd  add     rsp, 48h
0x1800018c1  pop     rdi
0x1800018c2  pop     rsi
0x1800018c3  pop     rbp
0x1800018c4  pop     rbx
0x1800018c5  retn
```
