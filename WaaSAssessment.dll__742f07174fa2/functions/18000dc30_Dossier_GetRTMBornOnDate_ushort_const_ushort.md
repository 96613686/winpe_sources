# Dossier::GetRTMBornOnDate(ushort const *,ushort * *)

- ea: `0x18000dc30`
- end: `0x18000dd49`
- name: `?GetRTMBornOnDate@Dossier@@UEAAJPEBGPEAPEAG@Z`
- size: `281`
- prototype: `__int64 __fastcall(Dossier *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000dc30`
- `0x18000efec`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dca1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dossier::GetRTMBornOnDate(Dossier *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v5; // edi
  void *v6; // r15
  void *v7; // r14
  DWORD LastError; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  void *v12; // [rsp+28h] [rbp-20h] BYREF
  char v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  LPVOID pv; // [rsp+90h] [rbp+48h] BYREF

  pv = 0;
  v12 = 0;
  v13 = 1;
  v5 = (*(__int64 (__fastcall **)(Dossier *, const unsigned __int16 *, void **))(*(_QWORD *)this + 64LL))(
         this,
         a2,
         &v12);
  if ( v13 )
  {
    v6 = v12;
    v7 = pv;
    if ( pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(v7);
      SetLastError(LastError);
    }
    pv = v6;
  }
  if ( v5 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(Dossier *, LPVOID, unsigned __int16 **))(*(_QWORD *)this + 48LL))(this, pv, a3);
    v11 = v10;
    if ( v10 >= 0 )
    {
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
        (const char *)(unsigned int)v10,
        (int)&pv);
      if ( pv )
        CoTaskMemFree(pv);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)v5,
      (int)&pv);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x18000dc30  push    rbp
0x18000dc32  push    rbx
0x18000dc33  push    rsi
0x18000dc34  push    rdi
0x18000dc35  push    r12
0x18000dc37  push    r13
0x18000dc39  push    r14
0x18000dc3b  push    r15
0x18000dc3d  mov     rbp, rsp
0x18000dc40  sub     rsp, 48h
0x18000dc44  mov     r13, r8
0x18000dc47  mov     r12, rcx
0x18000dc4a  mov     [rbp+pv], 0
0x18000dc52  lea     rax, [rbp+pv]
0x18000dc56  mov     [rbp+var_28], rax
0x18000dc5a  mov     [rbp+var_20], 0
0x18000dc62  mov     [rbp+var_18], 1
0x18000dc66  mov     rax, [rcx]
0x18000dc69  lea     r8, [rbp+var_20]
0x18000dc6d  mov     rax, [rax+40h]
0x18000dc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc76  mov     edi, eax
0x18000dc78  cmp     [rbp+var_18], 0
0x18000dc7c  jz      short loc_18000DCAB
0x18000dc7e  mov     r15, [rbp+var_20]
0x18000dc82  mov     rsi, [rbp+var_28]
0x18000dc86  mov     r14, [rsi]
0x18000dc89  test    r14, r14
0x18000dc8c  jz      short loc_18000DCA8
0x18000dc8e  call    cs:__imp_GetLastError
0x18000dc94  mov     ebx, eax
0x18000dc96  mov     rcx, r14; pv
0x18000dc99  call    cs:__imp_CoTaskMemFree
0x18000dc9f  mov     ecx, ebx; dwErrCode
0x18000dca1  call    cs:__imp_SetLastError
0x18000dca7  nop
0x18000dca8  mov     [rsi], r15
0x18000dcab  test    edi, edi
0x18000dcad  jns     short loc_18000DCDC
0x18000dcaf  mov     rcx, [rbp+40h]; this
0x18000dcb3  mov     r9d, edi; char *
0x18000dcb6  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000dcbd  mov     edx, 19Dh; void *
0x18000dcc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcc7  nop
0x18000dcc8  mov     rcx, [rbp+pv]; pv
0x18000dccc  test    rcx, rcx
0x18000dccf  jz      short loc_18000DCD8
0x18000dcd1  call    cs:__imp_CoTaskMemFree
0x18000dcd7  nop
0x18000dcd8  mov     eax, edi
0x18000dcda  jmp     short loc_18000DD38
0x18000dcdc  mov     rax, [r12]
0x18000dce0  mov     r8, r13
0x18000dce3  mov     rdx, [rbp+pv]
0x18000dce7  mov     rcx, r12
0x18000dcea  mov     rax, [rax+30h]
0x18000dcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcf3  mov     ebx, eax
0x18000dcf5  test    eax, eax
0x18000dcf7  jns     short loc_18000DD26
0x18000dcf9  mov     rcx, [rbp+40h]; this
0x18000dcfd  mov     r9d, eax; char *
0x18000dd00  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000dd07  mov     edx, 19Fh; void *
0x18000dd0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd11  nop
0x18000dd12  mov     rcx, [rbp+pv]; pv
0x18000dd16  test    rcx, rcx
0x18000dd19  jz      short loc_18000DD22
0x18000dd1b  call    cs:__imp_CoTaskMemFree
0x18000dd21  nop
0x18000dd22  mov     eax, ebx
0x18000dd24  jmp     short loc_18000DD38
0x18000dd26  mov     rcx, [rbp+pv]; pv
0x18000dd2a  test    rcx, rcx
0x18000dd2d  jz      short loc_18000DD36
0x18000dd2f  call    cs:__imp_CoTaskMemFree
0x18000dd35  nop
0x18000dd36  xor     eax, eax
0x18000dd38  add     rsp, 48h
0x18000dd3c  pop     r15
0x18000dd3e  pop     r14
0x18000dd40  pop     r13
0x18000dd42  pop     r12
0x18000dd44  pop     rdi
0x18000dd45  pop     rsi
0x18000dd46  pop     rbx
0x18000dd47  pop     rbp
0x18000dd48  retn
```
