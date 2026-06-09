# Enrollments::FindBySid(void * const,std::vector<std::vector<uchar,std::allocator<uchar>>,std::allocator<std::vector<uchar,std::allocator<uchar>>>> *)

- ea: `0x140061a60`
- end: `0x140061b28`
- name: `?FindBySid@Enrollments@@QEBAJQEAXPEAV?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, void *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140056780`

## callees

- `0x14000a420`
- `0x14000d5d0`
- `0x140054180`
- `0x14005eb98`
- `0x14005f5a4`
- `0x14005fa08`
- `0x140061a60`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x140061a8e`
- `ntdll!RtlEqualSid` at `0x140061a8e`

## string_xrefs

- `0x140061af0`: `onecore\ds\security\biometrics\service\trustlet\exe\secureenrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Enrollments::FindBySid(__int64 a1, void *a2, __int64 a3)
{
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 i; // rbx
  unsigned int v8; // ebx
  __int64 v10; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+28h] [rbp-40h]
  __int64 v12; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v10);
  v6 = *(_QWORD *)(v5 + 40);
  for ( i = *(_QWORD *)(v5 + 32); i != v6; i += 128 )
  {
    if ( RtlEqualSid(a2, *(PSID *)(i + 32)) )
    {
      if ( v11 == v12 )
      {
        std::vector<std::vector<unsigned char>>::_Emplace_reallocate<std::vector<unsigned char> const &>(
          &v10,
          v11,
          i + 8);
      }
      else
      {
        std::vector<unsigned char>::vector<unsigned char>(v11, i + 8);
        v11 += 24;
      }
    }
  }
  if ( v10 == v11 )
  {
    v8 = -2146861025;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x364,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\secureenrollments.cpp",
      (const char *)0x8009801FLL,
      v10);
  }
  else
  {
    std::vector<std::vector<unsigned char>>::operator=(a3, &v10);
    v8 = 0;
  }
  std::vector<std::vector<unsigned char>>::_Tidy(&v10);
  return v8;
}

```

## disassembly

```asm
0x140061a60  push    rbx
0x140061a62  push    rbp
0x140061a63  push    rsi
0x140061a64  push    rdi
0x140061a65  sub     rsp, 48h
0x140061a69  mov     rsi, r8
0x140061a6c  mov     rbp, rdx
0x140061a6f  mov     r9, rcx
0x140061a72  lea     rcx, [rsp+68h+var_48]
0x140061a77  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140061a7c  nop
0x140061a7d  mov     rdi, [r9+28h]
0x140061a81  mov     rbx, [r9+20h]
0x140061a85  jmp     short loc_140061AD2
0x140061a87  mov     rdx, [rbx+20h]; Sid2
0x140061a8b  mov     rcx, rbp; Sid1
0x140061a8e  call    cs:__imp_RtlEqualSid
0x140061a95  nop     dword ptr [rax+rax+00h]
0x140061a9a  test    al, al
0x140061a9c  jz      short loc_140061ACE
0x140061a9e  lea     r8, [rbx+8]
0x140061aa2  mov     rax, [rsp+68h+var_40]
0x140061aa7  cmp     rax, [rsp+68h+var_38]
0x140061aac  jz      short loc_140061AC1
0x140061aae  mov     rdx, r8
0x140061ab1  mov     rcx, rax
0x140061ab4  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x140061ab9  add     [rsp+68h+var_40], 18h
0x140061abf  jmp     short loc_140061ACE
0x140061ac1  mov     rdx, rax
0x140061ac4  lea     rcx, [rsp+68h+var_48]
0x140061ac9  call    ??$_Emplace_reallocate@AEBV?$vector@EV?$allocator@E@std@@@std@@@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAPEAV?$vector@EV?$allocator@E@std@@@1@QEAV21@AEBV21@@Z; std::vector<std::vector<uchar>>::_Emplace_reallocate<std::vector<uchar> const &>(std::vector<uchar> * const,std::vector<uchar> const &)
0x140061ace  sub     rbx, 0FFFFFFFFFFFFFF80h
0x140061ad2  cmp     rbx, rdi
0x140061ad5  jnz     short loc_140061A87
0x140061ad7  mov     rax, [rsp+68h+var_40]
0x140061adc  cmp     [rsp+68h+var_48], rax
0x140061ae1  jnz     short loc_140061B03
0x140061ae3  mov     rcx, [rsp+68h]; this
0x140061ae8  mov     ebx, 8009801Fh
0x140061aed  mov     r9d, ebx; char *
0x140061af0  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\biometrics\\serv"...
0x140061af7  mov     edx, 364h; void *
0x140061afc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140061b01  jmp     short loc_140061B12
0x140061b03  lea     rdx, [rsp+68h+var_48]
0x140061b08  mov     rcx, rsi
0x140061b0b  call    ??4?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::vector<uchar>>::operator=(std::vector<std::vector<uchar>> &&)
0x140061b10  xor     ebx, ebx
0x140061b12  lea     rcx, [rsp+68h+var_48]
0x140061b17  call    ?_Tidy@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::vector<uchar>>::_Tidy(void)
0x140061b1c  mov     eax, ebx
0x140061b1e  add     rsp, 48h
0x140061b22  pop     rdi
0x140061b23  pop     rsi
0x140061b24  pop     rbp
0x140061b25  pop     rbx
0x140061b26  retn
```
