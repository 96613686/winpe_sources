# WNFNotificationDispatcher::Enqueue(ActionType)

- ea: `0x18000b668`
- end: `0x18000b7d1`
- name: `?Enqueue@WNFNotificationDispatcher@@QEAA_NW4ActionType@@@Z`
- size: `361`
- prototype: `char __fastcall(int *, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180003b50`
- `0x180005f40`
- `0x180006598`
- `0x180007534`
- `0x180009934`

## callees

- `0x180001054`
- `0x180001218`
- `0x1800012f0`
- `0x180002a70`
- `0x180005840`
- `0x18000b668`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b693`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b693`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b7a5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b7a5`

## pseudocode

```c
char __fastcall WNFNotificationDispatcher::Enqueue(int *a1, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  bool v5; // zf
  char v6; // bl
  int v7; // r8d
  struct _RTL_CRITICAL_SECTION *v8; // r9
  int v10; // [rsp+30h] [rbp-49h] BYREF
  int v11; // [rsp+34h] [rbp-45h] BYREF
  int v12; // [rsp+38h] [rbp-41h] BYREF
  struct _RTL_CRITICAL_SECTION *v13[12]; // [rsp+40h] [rbp-39h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 4);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 4));
  v5 = *((_QWORD *)a1 + 8) == 0;
  v13[0] = v2;
  if ( v5 )
  {
    if ( (unsigned int)dword_18001C010 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    {
      v10 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18001C010,
        (__int64)&word_180016A26,
        0,
        0);
    }
    v6 = 0;
  }
  else
  {
    v6 = 1;
    *a1 |= a2;
    if ( (a2 & 1) != 0 )
    {
      a2 &= ~0x10u;
    }
    else if ( (a2 & 0x10) != 0 )
    {
      a2 &= ~1u;
    }
    if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    {
      v10 = *a1;
      v11 = v7;
      v13[10] = (struct _RTL_CRITICAL_SECTION *)&v10;
      v13[11] = v8;
      v13[8] = (struct _RTL_CRITICAL_SECTION *)&v11;
      v13[6] = (struct _RTL_CRITICAL_SECTION *)&v12;
      v13[9] = v8;
      v13[7] = v8;
      v12 = a2;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, qword_180016A80, 0, 0);
    }
    if ( *a1 && !*((_BYTE *)a1 + 57) && *((_BYTE *)a1 + 56) )
    {
      SubmitThreadpoolWork(*((PTP_WORK *)a1 + 8));
      *((_BYTE *)a1 + 57) = 1;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v13);
  return v6;
}

```

## disassembly

```asm
0x18000b668  push    rbp
0x18000b66a  push    rbx
0x18000b66b  push    rsi
0x18000b66c  push    rdi
0x18000b66d  lea     rbp, [rsp-3Fh]
0x18000b672  sub     rsp, 0B8h
0x18000b679  mov     rax, cs:__security_cookie
0x18000b680  xor     rax, rsp
0x18000b683  mov     [rbp+57h+var_30], rax
0x18000b687  lea     rbx, [rcx+10h]
0x18000b68b  mov     rdi, rcx
0x18000b68e  mov     rcx, rbx; lpCriticalSection
0x18000b691  mov     esi, edx
0x18000b693  call    cs:__imp_EnterCriticalSection
0x18000b699  cmp     qword ptr [rdi+40h], 0
0x18000b69e  mov     [rbp+57h+var_90], rbx
0x18000b6a2  jnz     short loc_18000B6F0
0x18000b6a4  mov     eax, cs:dword_18001C010
0x18000b6aa  cmp     eax, 3
0x18000b6ad  jbe     short loc_18000B6E9
0x18000b6af  mov     edx, 1
0x18000b6b4  lea     rcx, dword_18001C010
0x18000b6bb  call    _tlgKeywordOn
0x18000b6c0  test    al, al
0x18000b6c2  jz      short loc_18000B6E9
0x18000b6c4  lea     rax, [rbp+57h+var_A0]
0x18000b6c8  mov     [rbp+57h+var_A0], esi
0x18000b6cb  xor     r9d, r9d
0x18000b6ce  mov     [rsp+0D0h+var_B0], rax
0x18000b6d3  xor     r8d, r8d
0x18000b6d6  lea     rdx, word_180016A26
0x18000b6dd  lea     rcx, dword_18001C010
0x18000b6e4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000b6e9  xor     bl, bl
0x18000b6eb  jmp     loc_18000B7AE
0x18000b6f0  mov     r8d, [rdi]
0x18000b6f3  mov     ebx, 1
0x18000b6f8  mov     eax, r8d
0x18000b6fb  or      eax, esi
0x18000b6fd  mov     [rdi], eax
0x18000b6ff  test    bl, sil
0x18000b702  jz      short loc_18000B709
0x18000b704  and     esi, 0FFFFFFEFh
0x18000b707  jmp     short loc_18000B712
0x18000b709  test    sil, 10h
0x18000b70d  jz      short loc_18000B712
0x18000b70f  and     esi, 0FFFFFFFEh
0x18000b712  mov     eax, cs:dword_18001C010
0x18000b718  mov     r9d, 4
0x18000b71e  cmp     eax, r9d
0x18000b721  jbe     short loc_18000B790
0x18000b723  mov     rdx, rbx
0x18000b726  lea     rcx, dword_18001C010
0x18000b72d  call    _tlgKeywordOn
0x18000b732  test    al, al
0x18000b734  jz      short loc_18000B790
0x18000b736  mov     eax, [rdi]
0x18000b738  lea     rdx, qword_180016A80
0x18000b73f  mov     [rbp+57h+var_A0], eax
0x18000b742  lea     rcx, dword_18001C010
0x18000b749  lea     rax, [rbp+57h+var_A0]
0x18000b74d  mov     [rbp+57h+var_9C], r8d
0x18000b751  mov     [rbp+57h+var_40], rax
0x18000b755  xor     r8d, r8d
0x18000b758  lea     rax, [rbp+57h+var_9C]
0x18000b75c  mov     [rbp+57h+var_38], r9
0x18000b760  mov     [rbp+57h+var_50], rax
0x18000b764  lea     rax, [rbp+57h+var_98]
0x18000b768  mov     [rbp+57h+var_60], rax
0x18000b76c  lea     rax, [rbp+57h+var_80]
0x18000b770  mov     [rbp+57h+var_48], r9
0x18000b774  mov     [rbp+57h+var_58], r9
0x18000b778  xor     r9d, r9d
0x18000b77b  mov     [rsp+0D0h+var_A8], rax
0x18000b780  mov     dword ptr [rsp+0D0h+var_B0], 5
0x18000b788  mov     [rbp+57h+var_98], esi
0x18000b78b  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b790  cmp     dword ptr [rdi], 0
0x18000b793  jz      short loc_18000B7AE
0x18000b795  cmp     byte ptr [rdi+39h], 0
0x18000b799  jnz     short loc_18000B7AE
0x18000b79b  cmp     byte ptr [rdi+38h], 0
0x18000b79f  jz      short loc_18000B7AE
0x18000b7a1  mov     rcx, [rdi+40h]; pwk
0x18000b7a5  call    cs:__imp_SubmitThreadpoolWork
0x18000b7ab  mov     [rdi+39h], bl
0x18000b7ae  lea     rcx, [rbp+57h+var_90]
0x18000b7b2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000b7b7  mov     al, bl
0x18000b7b9  mov     rcx, [rbp+57h+var_30]
0x18000b7bd  xor     rcx, rsp; StackCookie
0x18000b7c0  call    __security_check_cookie
0x18000b7c5  add     rsp, 0B8h
0x18000b7cc  pop     rdi
0x18000b7cd  pop     rsi
0x18000b7ce  pop     rbx
0x18000b7cf  pop     rbp
0x18000b7d0  retn
```
