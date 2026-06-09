# Microsoft::DiagnosticsHub::StandardCollector::AgentWrapper_v1::OnGetGraphDataUpdates(ushort * const,ulong *,CollectorGraphPoint * * const)

- ea: `0x18000be10`
- end: `0x18000bf3e`
- name: `?OnGetGraphDataUpdates@AgentWrapper_v1@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJQEAGPEAKQEAPEAUCollectorGraphPoint@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::AgentWrapper_v1 *__hidden this, unsigned __int16 *const, unsigned int *, struct CollectorGraphPoint **const)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000be10`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18000beae`
- `VCRUNTIME140!memset` at `0x18000beae`
- `ole32!CoTaskMemAlloc` at `0x18000be92`
- `ole32!CoTaskMemAlloc` at `0x18000be92`
- `ole32!CoTaskMemFree` at `0x18000bf13`
- `ole32!CoTaskMemFree` at `0x18000bf1f`
- `ole32!CoTaskMemFree` at `0x18000bf13`
- `ole32!CoTaskMemFree` at `0x18000bf1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::AgentWrapper_v1::OnGetGraphDataUpdates(
        Microsoft::DiagnosticsHub::StandardCollector::AgentWrapper_v1 *this,
        unsigned __int16 *const a2,
        unsigned int *a3,
        struct CollectorGraphPoint **const a4)
{
  int v6; // edi
  struct CollectorGraphPoint *v7; // rbx
  unsigned __int64 v8; // rcx
  void *v9; // rax
  unsigned int v10; // r8d
  struct CollectorGraphPoint *v11; // r9
  unsigned int i; // eax
  __int64 v13; // rdx
  char *v14; // rcx
  LPVOID pv; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T cb; // [rsp+38h] [rbp-40h] BYREF

  LODWORD(cb) = 0;
  pv = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *const, LPVOID *, SIZE_T *))(**((_QWORD **)this + 5) + 88LL))(
         *((_QWORD *)this + 5),
         a2,
         &pv,
         &cb);
  if ( v6 >= 0 )
  {
    v7 = 0;
    LODWORD(v8) = cb;
    if ( (_DWORD)cb
      && (0xFFFFFFFFFFFFFFFFuLL / (unsigned int)cb < 0x20 || (v8 = 32LL * (unsigned int)cb, v8 > 0x7FFFFFFF))
      || (v9 = CoTaskMemAlloc((unsigned int)v8), (v7 = (struct CollectorGraphPoint *)v9) == 0) )
    {
      v6 = -2147024882;
    }
    else
    {
      memset(v9, 0, 32LL * (unsigned int)cb);
      v10 = 0;
      v11 = v7;
      for ( i = cb; v10 < (unsigned int)cb; i = cb )
      {
        v13 = 32LL * v10;
        v14 = (char *)pv;
        *(_QWORD *)((char *)v7 + v13) = *(_QWORD *)((char *)pv + v13);
        *(_QWORD *)((char *)v7 + v13 + 8) = *(_QWORD *)&v14[v13 + 8];
        *(_QWORD *)((char *)v7 + v13 + 24) = *(_QWORD *)&v14[v13 + 24];
        *(_QWORD *)((char *)v7 + v13 + 16) = *(_QWORD *)&v14[v13 + 16];
        ++v10;
      }
      *a3 = i;
      v7 = 0;
      *a4 = v11;
      v6 = 0;
    }
    CoTaskMemFree(v7);
  }
  CoTaskMemFree(pv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000be10  push    rbx
0x18000be12  push    rsi
0x18000be13  push    rdi
0x18000be14  push    r14
0x18000be16  sub     rsp, 58h
0x18000be1a  mov     rax, cs:__security_cookie
0x18000be21  xor     rax, rsp
0x18000be24  mov     [rsp+78h+var_38], rax
0x18000be29  mov     r14, r9
0x18000be2c  mov     rsi, r8
0x18000be2f  mov     dword ptr [rsp+78h+cb], 0
0x18000be37  mov     [rsp+78h+pv], 0
0x18000be40  mov     rcx, [rcx+28h]
0x18000be44  mov     rax, [rcx]
0x18000be47  lea     r9, [rsp+78h+cb]
0x18000be4c  lea     r8, [rsp+78h+pv]
0x18000be51  mov     rax, [rax+58h]
0x18000be55  call    cs:__guard_dispatch_icall_fptr
0x18000be5b  mov     edi, eax
0x18000be5d  test    eax, eax
0x18000be5f  js      loc_18000BF1A
0x18000be65  xor     ebx, ebx
0x18000be67  mov     ecx, dword ptr [rsp+78h+cb]
0x18000be6b  test    rcx, rcx
0x18000be6e  jz      short loc_18000BE90
0x18000be70  xor     edx, edx
0x18000be72  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000be76  div     rcx
0x18000be79  cmp     rax, 20h ; ' '
0x18000be7d  jb      loc_18000BF0B
0x18000be83  shl     rcx, 5
0x18000be87  cmp     rcx, 7FFFFFFFh
0x18000be8e  ja      short loc_18000BF0B
0x18000be90  mov     ecx, ecx; cb
0x18000be92  call    cs:__imp_CoTaskMemAlloc
0x18000be98  mov     rbx, rax
0x18000be9b  test    rax, rax
0x18000be9e  jz      short loc_18000BF0B
0x18000bea0  mov     r8d, dword ptr [rsp+78h+cb]
0x18000bea5  shl     r8, 5; Size
0x18000bea9  xor     edx, edx; Val
0x18000beab  mov     rcx, rax; void *
0x18000beae  call    cs:__imp_memset
0x18000beb4  xor     r8d, r8d
0x18000beb7  mov     r9, rbx
0x18000beba  mov     eax, dword ptr [rsp+78h+cb]
0x18000bebe  test    eax, eax
0x18000bec0  jz      short loc_18000BF00
0x18000bec2  mov     edx, r8d
0x18000bec5  shl     rdx, 5
0x18000bec9  mov     rcx, [rsp+78h+pv]
0x18000bece  mov     rax, [rdx+rcx]
0x18000bed2  mov     [rdx+rbx], rax
0x18000bed6  mov     rax, [rdx+rcx+8]
0x18000bedb  mov     [rdx+rbx+8], rax
0x18000bee0  mov     rax, [rdx+rcx+18h]
0x18000bee5  mov     [rdx+rbx+18h], rax
0x18000beea  mov     rax, [rdx+rcx+10h]
0x18000beef  mov     [rdx+rbx+10h], rax
0x18000bef4  inc     r8d
0x18000bef7  mov     eax, dword ptr [rsp+78h+cb]
0x18000befb  cmp     r8d, eax
0x18000befe  jb      short loc_18000BEC2
0x18000bf00  mov     [rsi], eax
0x18000bf02  xor     ebx, ebx
0x18000bf04  mov     [r14], r9
0x18000bf07  xor     edi, edi
0x18000bf09  jmp     short loc_18000BF10
0x18000bf0b  mov     edi, 8007000Eh
0x18000bf10  mov     rcx, rbx; pv
0x18000bf13  call    cs:__imp_CoTaskMemFree
0x18000bf19  nop
0x18000bf1a  mov     rcx, [rsp+78h+pv]; pv
0x18000bf1f  call    cs:__imp_CoTaskMemFree
0x18000bf25  mov     eax, edi
0x18000bf27  mov     rcx, [rsp+78h+var_38]
0x18000bf2c  xor     rcx, rsp; StackCookie
0x18000bf2f  call    __security_check_cookie
0x18000bf34  add     rsp, 58h
0x18000bf38  pop     r14
0x18000bf3a  pop     rdi
0x18000bf3b  pop     rsi
0x18000bf3c  pop     rbx
0x18000bf3d  retn
```
