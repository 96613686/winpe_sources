# Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::SetAt(uint,HSTRING__ *)

- ea: `0x1800c9aa0`
- end: `0x1800c9c6c`
- name: `?SetAt@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUHSTRING__@@@Z`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18002b244`
- `0x18002f1e8`
- `0x18003f730`
- `0x180043620`
- `0x180046900`
- `0x180047250`
- `0x1800aabd8`
- `0x1800c9aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9be1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9be1`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c9b22`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c9b91`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c9b22`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c9b91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9bb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9bf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9bb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9bf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9c08`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::SetAt(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // r14
  int v4; // ebx
  HSTRING v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rax
  RTL_SRWLOCK *v8; // rcx
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  RTL_SRWLOCK *v11; // [rsp+38h] [rbp-28h] BYREF
  int v12; // [rsp+40h] [rbp-20h] BYREF
  _DWORD *v13; // [rsp+48h] [rbp-18h]
  _BYTE v14[16]; // [rsp+50h] [rbp-10h] BYREF
  HSTRING Destination; // [rsp+98h] [rbp+38h] BYREF

  v2 = a2;
  LODWORD(Destination) = 0;
  v12 = -2147483627;
  v13 = 0;
  XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
  v4 = (int)Destination;
  v5 = 0;
  if ( (int)Destination >= 0 )
  {
    XWinRT::SerializingLockPolicy::Write(&v11, a1 + 128, &Destination);
    v4 = (int)Destination;
    if ( (int)Destination >= 0 )
    {
      if ( (unsigned int)v2 >= *(_DWORD *)(a1 + 96) )
      {
        v4 = -2147483637;
        RoOriginateError(2147483659LL, 0);
      }
      if ( v4 >= 0 )
      {
        v6 = XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(v14, *(unsigned int *)(a1 + 176), a1 + 180);
        XWinRT::detail::ReentrancyGuard<1>::operator=(&v12, v6);
        v4 = XWinRT::detail::ReentrancyGuard<1>::hr(&v12);
        if ( v4 >= 0 )
        {
          v7 = *(_QWORD *)(a1 + 112);
          Destination = 0;
          if ( memmove_s_0(&Destination, 8u, (const void *const)(v7 + 8 * v2), 8u) )
          {
            v4 = -2147418113;
            RoOriginateError(2147549183LL, 0);
          }
          else
          {
            *(_QWORD *)(*(_QWORD *)(a1 + 112) + 8 * v2) = string;
            ++*(_DWORD *)(a1 + 144);
            string = 0;
            WindowsDeleteString(0);
            v5 = Destination;
          }
        }
      }
    }
    if ( v11 )
    {
      v8 = v11 + 1;
      if ( LODWORD(v11->Ptr) == 1 )
        LODWORD(v8->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v8);
    }
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v5);
  if ( v4 >= 0 )
    v4 = Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>::RaiseEvent(
           (unsigned int)&v12,
           (int)a1 + 152,
           a1 != 0 ? a1 + 16 : 0,
           3,
           v2);
  if ( v13 )
    *v13 = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c9aa0  mov     [rsp-18h+arg_0], rbx
0x1800c9aa5  mov     [rsp-18h+arg_8], rsi
0x1800c9aaa  mov     [rsp-18h+arg_10], r8
0x1800c9aaf  push    rbp
0x1800c9ab0  push    rdi
0x1800c9ab1  push    r14
0x1800c9ab3  mov     rbp, rsp
0x1800c9ab6  sub     rsp, 60h
0x1800c9aba  mov     r14d, edx
0x1800c9abd  lea     r8, [rbp+Destination]
0x1800c9ac1  mov     rsi, rcx
0x1800c9ac4  mov     dword ptr [rbp+Destination], 0
0x1800c9acb  lea     rdx, [rbp+arg_10]
0x1800c9acf  mov     [rbp+var_20], 80000015h
0x1800c9ad6  lea     rcx, [rbp+string]; newString
0x1800c9ada  mov     [rbp+var_18], 0
0x1800c9ae2  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x1800c9ae7  mov     ebx, dword ptr [rbp+Destination]
0x1800c9aea  xor     edi, edi
0x1800c9aec  test    ebx, ebx
0x1800c9aee  js      loc_1800C9BED
0x1800c9af4  lea     rdx, [rsi+80h]
0x1800c9afb  lea     r8, [rbp+Destination]
0x1800c9aff  lea     rcx, [rbp+var_28]
0x1800c9b03  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x1800c9b08  mov     ebx, dword ptr [rbp+Destination]
0x1800c9b0b  test    ebx, ebx
0x1800c9b0d  js      loc_1800C9BC7
0x1800c9b13  cmp     r14d, [rsi+60h]
0x1800c9b17  jb      short loc_1800C9B2E
0x1800c9b19  mov     ebx, 8000000Bh
0x1800c9b1e  xor     edx, edx
0x1800c9b20  mov     ecx, ebx
0x1800c9b22  call    cs:__imp_RoOriginateError
0x1800c9b29  nop     dword ptr [rax+rax+00h]
0x1800c9b2e  test    ebx, ebx
0x1800c9b30  js      loc_1800C9BC7
0x1800c9b36  mov     edx, [rsi+0B0h]
0x1800c9b3c  lea     r8, [rsi+0B4h]
0x1800c9b43  lea     rcx, [rbp+var_10]
0x1800c9b47  call    ??0?$ReentrancyGuard@$00@detail@XWinRT@@QEAA@JPECJ@Z; XWinRT::detail::ReentrancyGuard<1>::ReentrancyGuard<1>(long,long volatile *)
0x1800c9b4c  mov     rdx, rax
0x1800c9b4f  lea     rcx, [rbp+var_20]
0x1800c9b53  call    ??4?$ReentrancyGuard@$00@detail@XWinRT@@QEAAAEAU012@U012@@Z; XWinRT::detail::ReentrancyGuard<1>::operator=(XWinRT::detail::ReentrancyGuard<1>)
0x1800c9b58  lea     rcx, [rbp+var_20]
0x1800c9b5c  call    ?hr@?$ReentrancyGuard@$00@detail@XWinRT@@QEAAJXZ; XWinRT::detail::ReentrancyGuard<1>::hr(void)
0x1800c9b61  mov     ebx, eax
0x1800c9b63  test    eax, eax
0x1800c9b65  js      short loc_1800C9BC7
0x1800c9b67  mov     rax, [rsi+70h]
0x1800c9b6b  lea     rcx, [rbp+Destination]; Destination
0x1800c9b6f  mov     edx, 8; DestinationSize
0x1800c9b74  mov     [rbp+Destination], rdi
0x1800c9b78  mov     r9d, edx; SourceSize
0x1800c9b7b  lea     r8, [rax+r14*8]; Source
0x1800c9b7f  call    memmove_s_0
0x1800c9b84  test    eax, eax
0x1800c9b86  jz      short loc_1800C9B9F
0x1800c9b88  mov     ebx, 8000FFFFh
0x1800c9b8d  xor     edx, edx
0x1800c9b8f  mov     ecx, ebx
0x1800c9b91  call    cs:__imp_RoOriginateError
0x1800c9b98  nop     dword ptr [rax+rax+00h]
0x1800c9b9d  jmp     short loc_1800C9BC7
0x1800c9b9f  mov     rcx, [rsi+70h]
0x1800c9ba3  mov     rax, [rbp+string]
0x1800c9ba7  mov     [rcx+r14*8], rax
0x1800c9bab  xor     ecx, ecx; string
0x1800c9bad  inc     dword ptr [rsi+90h]
0x1800c9bb3  mov     [rbp+string], rdi
0x1800c9bb7  call    cs:__imp_WindowsDeleteString
0x1800c9bbe  nop     dword ptr [rax+rax+00h]
0x1800c9bc3  mov     rdi, [rbp+Destination]
0x1800c9bc7  mov     rax, [rbp+var_28]
0x1800c9bcb  test    rax, rax
0x1800c9bce  jz      short loc_1800C9BED
0x1800c9bd0  cmp     dword ptr [rax], 1
0x1800c9bd3  lea     rcx, [rax+8]; SRWLock
0x1800c9bd7  jnz     short loc_1800C9BE1
0x1800c9bd9  add     dword ptr [rcx], 10000000h
0x1800c9bdf  jmp     short loc_1800C9BED
0x1800c9be1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c9be8  nop     dword ptr [rax+rax+00h]
0x1800c9bed  mov     rcx, [rbp+string]; string
0x1800c9bf1  call    cs:__imp_WindowsDeleteString
0x1800c9bf8  nop     dword ptr [rax+rax+00h]
0x1800c9bfd  mov     rcx, rdi; string
0x1800c9c00  mov     [rbp+string], 0
0x1800c9c08  call    cs:__imp_WindowsDeleteString
0x1800c9c0f  nop     dword ptr [rax+rax+00h]
0x1800c9c14  test    ebx, ebx
0x1800c9c16  js      short loc_1800C9C45
0x1800c9c18  lea     rcx, [rsi+10h]
0x1800c9c1c  mov     [rsp+60h+var_40], r14d
0x1800c9c21  mov     rax, rsi
0x1800c9c24  lea     rdx, [rsi+98h]
0x1800c9c2b  neg     rax
0x1800c9c2e  mov     r9d, 3
0x1800c9c34  sbb     r8, r8
0x1800c9c37  and     r8, rcx
0x1800c9c3a  lea     rcx, [rbp+var_20]
0x1800c9c3e  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@Internal@Collections@Foundation@Windows@@SAJAEAU?$ReentrancyGuard@$00@detail@XWinRT@@AEAV?$GitEventSource@U?$VectorChangedEventHandler@PEAUHSTRING__@@@Collections@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@25@PEAU?$IObservableVector@PEAUHSTRING__@@@345@W4CollectionChange@345@I@Z; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>::RaiseEvent(XWinRT::detail::ReentrancyGuard<1> &,Windows::Internal::GitEventSource<Windows::Foundation::Collections::VectorChangedEventHandler<HSTRING__ *>,Microsoft::WRL::InvokeModeOptions<-2>> &,Windows::Foundation::Collections::IObservableVector<HSTRING__ *> *,Windows::Foundation::Collections::CollectionChange,uint)
0x1800c9c43  mov     ebx, eax
0x1800c9c45  mov     rax, [rbp+var_18]
0x1800c9c49  test    rax, rax
0x1800c9c4c  jz      short loc_1800C9C54
0x1800c9c4e  mov     dword ptr [rax], 0
0x1800c9c54  lea     r11, [rsp+60h+var_s0]
0x1800c9c59  mov     eax, ebx
0x1800c9c5b  mov     rbx, [r11+20h]
0x1800c9c5f  mov     rsi, [r11+28h]
0x1800c9c63  mov     rsp, r11
0x1800c9c66  pop     r14
0x1800c9c68  pop     rdi
0x1800c9c69  pop     rbp
0x1800c9c6a  retn
```
