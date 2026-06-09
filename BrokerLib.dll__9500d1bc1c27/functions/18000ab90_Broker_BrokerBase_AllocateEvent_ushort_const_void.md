# Broker::BrokerBase::AllocateEvent(ushort const *,void *)

- ea: `0x18000ab90`
- end: `0x18000ae1c`
- name: `?AllocateEvent@BrokerBase@Broker@@AEAAPEAU_BROKERED_EVENT@@PEBGPEAX@Z`
- size: `652`
- prototype: `struct _BROKERED_EVENT *(Broker::BrokerBase *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014f50`
- `0x180017a9c`

## callees

- `0x180005b50`
- `0x18000ab90`
- `0x1800165aa`
- `0x1800165da`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000abd0`
- `ntdll!RtlLengthSid` at `0x18000abd0`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad6c`
- `ntdll!RtlNtStatusToDosError` at `0x18000ade4`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad6c`
- `ntdll!RtlNtStatusToDosError` at `0x18000ade4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ac4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ac4b`

## pseudocode

```c
struct _BROKERED_EVENT *__fastcall Broker::BrokerBase::AllocateEvent(
        Broker::BrokerBase *this,
        const unsigned __int16 *a2,
        void *a3)
{
  unsigned __int64 v5; // rsi
  size_t v6; // r8
  NTSTATUS v7; // r14d
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rdx
  NTSTATUS v10; // ecx
  __int64 v11; // rsi
  size_t v12; // rbx
  size_t v13; // rbp
  HANDLE ProcessHeap; // rax
  char *v15; // rax
  char *v16; // rbx
  _WORD *v17; // r8
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  _WORD *v20; // rcx
  char *v21; // rcx
  __int64 v23; // r9
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  __int128 v25; // [rsp+28h] [rbp-40h]
  int v26; // [rsp+38h] [rbp-30h]
  ULONG v27; // [rsp+40h] [rbp-28h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v23 = 0;
    if ( *((_QWORD *)this + 1) )
      v23 = *((_QWORD *)this + 1);
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, v23);
  }
  if ( !a3 )
  {
    v26 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v25 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  v5 = 0;
  v6 = RtlLengthSid(a3);
  v7 = -1073741811;
  if ( a2 )
  {
    v8 = a2;
    v9 = 1024;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v9;
    }
    while ( v9 );
    v10 = -1073741811;
    if ( v9 )
    {
      v10 = 0;
      v11 = 2 * (1024 - v9);
    }
    else
    {
      v11 = 0;
    }
    if ( !v9 )
    {
      v26 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v27 = RtlNtStatusToDosError(v10);
      v25 = 0;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    v5 = v11 + 2;
  }
  v12 = v6 + 56;
  v13 = v6;
  ProcessHeap = GetProcessHeap();
  v15 = (char *)HeapAlloc(ProcessHeap, 8u, v12 + v5);
  v16 = v15;
  if ( !v15 )
  {
    *((_QWORD *)&v25 + 1) = 0;
    *(_QWORD *)&v25 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  if ( a2 )
  {
    v17 = v15 + 56;
    v18 = v5 >> 1;
    *((_QWORD *)v15 + 3) = v15 + 56;
    if ( v5 >> 1 )
    {
      if ( v18 > 0x7FFFFFFF )
      {
        *v17 = 0;
      }
      else
      {
        v19 = 2147483646;
        do
        {
          if ( !v19 )
            break;
          if ( !*a2 )
            break;
          *v17++ = *a2++;
          --v19;
          --v18;
        }
        while ( v18 );
        v20 = v17 - 1;
        v7 = -2147483643;
        if ( v18 )
        {
          v20 = v17;
          v7 = 0;
        }
        *v20 = 0;
        if ( v18 )
          goto LABEL_23;
      }
    }
    v26 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v27 = RtlNtStatusToDosError(v7);
    v25 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
LABEL_23:
  v21 = &v16[v5 + 56];
  *((_QWORD *)v16 + 4) = v21;
  memcpy_0(v21, a3, v13);
  return (struct _BROKERED_EVENT *)v16;
}

```

## disassembly

```asm
0x18000ab90  push    rdi
0x18000ab92  push    r15
0x18000ab94  sub     rsp, 58h
0x18000ab98  mov     r15, r8
0x18000ab9b  mov     rdi, rdx
0x18000ab9e  mov     rax, rcx
0x18000aba1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aba8  test    dword ptr [rcx+1Ch], 800h
0x18000abaf  jnz     loc_18000AD05
0x18000abb5  test    r15, r15
0x18000abb8  jz      loc_18000AD37
0x18000abbe  mov     [rsp+68h+arg_10], rsi
0x18000abc6  mov     rcx, r15; Sid
0x18000abc9  mov     [rsp+68h+var_18], r14
0x18000abce  xor     esi, esi
0x18000abd0  call    cs:__imp_RtlLengthSid
0x18000abd6  mov     r8d, eax
0x18000abd9  mov     r14d, 0C000000Dh
0x18000abdf  test    rdi, rdi
0x18000abe2  jz      short loc_18000AC28
0x18000abe4  mov     esi, 400h
0x18000abe9  mov     rcx, rdi
0x18000abec  mov     edx, esi
0x18000abee  xchg    ax, ax
0x18000abf0  cmp     word ptr [rcx], 0
0x18000abf4  jz      short loc_18000AC00
0x18000abf6  add     rcx, 2
0x18000abfa  sub     rdx, 1
0x18000abfe  jnz     short loc_18000ABF0
0x18000ac00  xor     eax, eax
0x18000ac02  mov     ecx, r14d
0x18000ac05  test    rdx, rdx
0x18000ac08  cmovnz  ecx, eax; Status
0x18000ac0b  jz      loc_18000AD65
0x18000ac11  sub     rsi, rdx
0x18000ac14  add     rsi, rsi
0x18000ac17  test    rdx, rdx
0x18000ac1a  cmovz   rsi, rax
0x18000ac1e  jz      loc_18000AD6C
0x18000ac24  add     rsi, 2
0x18000ac28  mov     [rsp+68h+arg_0], rbx
0x18000ac2d  lea     rbx, [r8+38h]
0x18000ac31  mov     [rsp+68h+arg_8], rbp
0x18000ac36  mov     rbp, r8
0x18000ac39  call    cs:__imp_GetProcessHeap
0x18000ac3f  lea     r8, [rbx+rsi]; dwBytes
0x18000ac43  mov     edx, 8; dwFlags
0x18000ac48  mov     rcx, rax; hHeap
0x18000ac4b  call    cs:__imp_HeapAlloc
0x18000ac51  mov     rbx, rax
0x18000ac54  test    rax, rax
0x18000ac57  jz      loc_18000ADA4
0x18000ac5d  test    rdi, rdi
0x18000ac60  jz      short loc_18000ACCD
0x18000ac62  mov     rdx, rsi
0x18000ac65  lea     r8, [rax+38h]
0x18000ac69  shr     rdx, 1
0x18000ac6c  mov     [rax+18h], r8
0x18000ac70  jz      loc_18000ADD6
0x18000ac76  cmp     rdx, 7FFFFFFFh
0x18000ac7d  ja      loc_18000ADDB
0x18000ac83  mov     eax, 7FFFFFFEh
0x18000ac88  test    rax, rax
0x18000ac8b  jz      short loc_18000ACAA
0x18000ac8d  movzx   ecx, word ptr [rdi]
0x18000ac90  test    cx, cx
0x18000ac93  jz      short loc_18000ACAA
0x18000ac95  mov     [r8], cx
0x18000ac99  add     rdi, 2
0x18000ac9d  add     r8, 2
0x18000aca1  dec     rax
0x18000aca4  sub     rdx, 1
0x18000aca8  jnz     short loc_18000AC88
0x18000acaa  test    rdx, rdx
0x18000acad  lea     rcx, [r8-2]
0x18000acb1  mov     r14d, 80000005h
0x18000acb7  cmovnz  rcx, r8
0x18000acbb  xor     eax, eax
0x18000acbd  test    rdx, rdx
0x18000acc0  cmovnz  r14d, eax
0x18000acc4  mov     [rcx], ax
0x18000acc7  jz      loc_18000ADE1
0x18000accd  lea     rcx, [rbx+38h]
0x18000acd1  mov     r8, rbp; Size
0x18000acd4  add     rcx, rsi; void *
0x18000acd7  mov     rdx, r15; Src
0x18000acda  mov     [rbx+20h], rcx
0x18000acde  call    memcpy_0
0x18000ace3  mov     rbp, [rsp+68h+arg_8]
0x18000ace8  mov     rax, rbx
0x18000aceb  mov     rbx, [rsp+68h+arg_0]
0x18000acf0  mov     rsi, [rsp+68h+arg_10]
0x18000acf8  mov     r14, [rsp+68h+var_18]
0x18000acfd  add     rsp, 58h
0x18000ad01  pop     r15
0x18000ad03  pop     rdi
0x18000ad04  retn
0x18000ad05  cmp     byte ptr [rcx+19h], 5
0x18000ad09  jb      loc_18000ABB5
0x18000ad0f  mov     rax, [rax+8]
0x18000ad13  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000ad1a  mov     rcx, [rcx+10h]
0x18000ad1e  xor     r9d, r9d
0x18000ad21  test    rax, rax
0x18000ad24  mov     edx, 1Bh
0x18000ad29  cmovnz  r9, rax
0x18000ad2d  call    WPP_SF__guid_
0x18000ad32  jmp     loc_18000ABB5
0x18000ad37  xorps   xmm0, xmm0
0x18000ad3a  mov     [rsp+68h+var_30], 4
0x18000ad42  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18000ad49  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000ad50  mov     [rsp+68h+pExceptionObject], rax
0x18000ad55  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000ad5a  movups  [rsp+68h+var_40], xmm0
0x18000ad5f  call    _CxxThrowException_0
0x18000ad65  xor     esi, esi
0x18000ad67  jmp     loc_18000AC17
0x18000ad6c  call    cs:__imp_RtlNtStatusToDosError
0x18000ad72  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000ad79  mov     [rsp+68h+var_30], 1
0x18000ad81  mov     [rsp+68h+pExceptionObject], rcx
0x18000ad86  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000ad8d  xorps   xmm0, xmm0
0x18000ad90  mov     [rsp+68h+var_28], eax
0x18000ad94  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000ad99  movups  [rsp+68h+var_40], xmm0
0x18000ad9e  call    _CxxThrowException_0
0x18000ada4  xorps   xmm0, xmm0
0x18000ada7  lea     rax, aBadAllocation; "bad allocation"
0x18000adae  movups  [rsp+68h+var_40], xmm0
0x18000adb3  mov     qword ptr [rsp+68h+var_40], rax
0x18000adb8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000adbf  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000adc6  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000adcb  mov     [rsp+68h+pExceptionObject], rax
0x18000add0  call    _CxxThrowException_0
0x18000add6  test    rdx, rdx
0x18000add9  jz      short loc_18000ADE1
0x18000addb  xor     eax, eax
0x18000addd  mov     [r8], ax
0x18000ade1  mov     ecx, r14d; Status
0x18000ade4  call    cs:__imp_RtlNtStatusToDosError
0x18000adea  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000adf1  mov     [rsp+68h+var_30], 1
0x18000adf9  mov     [rsp+68h+pExceptionObject], rcx
0x18000adfe  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000ae05  xorps   xmm0, xmm0
0x18000ae08  mov     [rsp+68h+var_28], eax
0x18000ae0c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000ae11  movups  [rsp+68h+var_40], xmm0
0x18000ae16  call    _CxxThrowException_0
```
