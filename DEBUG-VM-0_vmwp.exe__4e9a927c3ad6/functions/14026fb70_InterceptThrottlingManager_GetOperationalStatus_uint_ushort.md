# InterceptThrottlingManager::GetOperationalStatus(uint *,ushort * *)

- ea: `0x14026fb70`
- end: `0x14026fd49`
- name: `?GetOperationalStatus@InterceptThrottlingManager@@QEBAXPEAIPEAPEAG@Z`
- size: `473`
- prototype: `void __fastcall(InterceptThrottlingManager *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14026bc30`

## callees

- `0x140023f74`
- `0x14006af38`
- `0x140132940`
- `0x14026fb70`
- `0x14026fd50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fbd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fc1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fc71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fbd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fc1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14026fc71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14026fd02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14026fd02`

## string_xrefs

- `0x14026fbf2`: `onecore\vm\common\vml\VmMemory.h`
- `0x14026fc39`: `onecore\vm\common\vml\VmMemory.h`
- `0x14026fc8f`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall InterceptThrottlingManager::GetOperationalStatus(
        InterceptThrottlingManager *this,
        unsigned int *a2,
        unsigned __int16 **a3)
{
  unsigned int v5; // edi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // rax
  int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // esi
  unsigned __int16 *v12; // rax
  unsigned int v13; // r8d
  unsigned __int64 v14; // r9
  __int64 i; // rcx
  int v16; // [rsp+20h] [rbp-40h] BYREF
  __int128 v17; // [rsp+28h] [rbp-38h]
  __int128 v18; // [rsp+38h] [rbp-28h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v16 = 0;
  v18 = 0;
  v19 = 0;
  v17 = 0u;
  InterceptThrottlingManager::GetThrottlingState(this, &v16, &v18);
  v5 = 1;
  if ( (v16 & 1) != 0 )
  {
    if ( (v16 & 0xFFFFFFFB) == 3 )
    {
      v8 = (unsigned __int16 *)CoTaskMemAlloc(2u);
      v7 = v8;
      if ( !v8 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5FF,
          (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
          (const char *)0x8007000ELL,
          v16);
      *v8 = -25535;
    }
    else
    {
      v9 = v16 & 2;
      v10 = ((__int64)(*((_QWORD *)&v18 + 1) - v18) >> 2) + 1;
      if ( (v16 & 2) != 0 )
        v10 = (__int64)(*((_QWORD *)&v18 + 1) - v18) >> 2;
      v11 = v10;
      v12 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v10);
      v7 = v12;
      if ( !v12 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5FF,
          (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
          (const char *)0x8007000ELL,
          v16);
      v13 = 0;
      if ( !v9 )
      {
        *v12 = -25533;
        v13 = 1;
      }
      v14 = 0;
      for ( i = v18; v14 < (__int64)(*((_QWORD *)&v18 + 1) - v18) >> 2; i = v18 )
        v12[v13++] = *((_WORD *)qword_140323650 + *(int *)(i + 4 * v14++));
      v5 = v11;
    }
  }
  else
  {
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2u);
    v7 = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5FF,
        (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
        (const char *)0x8007000ELL,
        v16);
    *v6 = -25534;
  }
  *a2 = v5;
  *a3 = v7;
  CoTaskMemFree(0);
  if ( (_QWORD)v18 )
    std::_Deallocate<16>(v18, (v19 - v18) & 0xFFFFFFFFFFFFFFFCuLL);
}

```

## disassembly

```asm
0x14026fb70  mov     [rsp-28h+arg_18], rbx
0x14026fb75  push    rbp
0x14026fb76  push    rsi
0x14026fb77  push    rdi
0x14026fb78  push    r14
0x14026fb7a  push    r15
0x14026fb7c  mov     rbp, rsp
0x14026fb7f  sub     rsp, 60h
0x14026fb83  mov     rax, cs:__security_cookie
0x14026fb8a  xor     rax, rsp
0x14026fb8d  mov     [rbp+var_10], rax
0x14026fb91  mov     r15, r8
0x14026fb94  mov     r14, rdx
0x14026fb97  mov     [rbp+var_40], 0
0x14026fb9e  xorps   xmm0, xmm0
0x14026fba1  xor     eax, eax
0x14026fba3  xorps   xmm1, xmm1
0x14026fba6  movdqu  [rbp+var_28], xmm1
0x14026fbab  mov     [rbp+var_18], rax
0x14026fbaf  movups  [rbp+var_38], xmm0
0x14026fbb3  mov     qword ptr [rbp+var_38], rax
0x14026fbb7  lea     r8, [rbp+var_28]
0x14026fbbb  lea     rdx, [rbp+var_40]
0x14026fbbf  call    ?GetThrottlingState@InterceptThrottlingManager@@QEBAXPEAUThrottleState@1@AEAV?$vector@W4__MIDL___MIDL_itf_vmbservices_0000_0011_0001@@V?$allocator@W4__MIDL___MIDL_itf_vmbservices_0000_0011_0001@@@std@@@std@@@Z; InterceptThrottlingManager::GetThrottlingState(InterceptThrottlingManager::ThrottleState *,std::vector<__MIDL___MIDL_itf_vmbservices_0000_0011_0001> &)
0x14026fbc4  mov     ebx, [rbp+var_40]
0x14026fbc7  mov     edi, 1
0x14026fbcc  test    dil, bl
0x14026fbcf  jnz     short loc_14026FC0E
0x14026fbd1  lea     ecx, [rdi+1]; cb
0x14026fbd4  call    cs:__imp_CoTaskMemAlloc
0x14026fbdb  nop     dword ptr [rax+rax+00h]
0x14026fbe0  mov     rdx, rax
0x14026fbe3  test    rax, rax
0x14026fbe6  jnz     short loc_14026FC04
0x14026fbe8  mov     rcx, [rbp+28h]; this
0x14026fbec  mov     r9d, 8007000Eh; char *
0x14026fbf2  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14026fbf9  mov     edx, 5FFh; void *
0x14026fbfe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14026fc04  mov     word ptr [rax], 9C42h
0x14026fc09  jmp     loc_14026FCFA
0x14026fc0e  mov     eax, ebx
0x14026fc10  and     eax, 0FFFFFFFBh
0x14026fc13  cmp     eax, 3
0x14026fc16  jnz     short loc_14026FC55
0x14026fc18  lea     ecx, [rax-1]; cb
0x14026fc1b  call    cs:__imp_CoTaskMemAlloc
0x14026fc22  nop     dword ptr [rax+rax+00h]
0x14026fc27  mov     rdx, rax
0x14026fc2a  test    rax, rax
0x14026fc2d  jnz     short loc_14026FC4B
0x14026fc2f  mov     rcx, [rbp+28h]; this
0x14026fc33  mov     r9d, 8007000Eh; char *
0x14026fc39  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14026fc40  mov     edx, 5FFh; void *
0x14026fc45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14026fc4b  mov     word ptr [rax], 9C41h
0x14026fc50  jmp     loc_14026FCFA
0x14026fc55  mov     rcx, qword ptr [rbp+var_28+8]
0x14026fc59  sub     rcx, qword ptr [rbp+var_28]
0x14026fc5d  sar     rcx, 2
0x14026fc61  and     ebx, 2
0x14026fc64  lea     eax, [rcx+1]
0x14026fc67  cmovnz  eax, ecx
0x14026fc6a  mov     esi, eax
0x14026fc6c  mov     ecx, eax
0x14026fc6e  add     rcx, rcx; cb
0x14026fc71  call    cs:__imp_CoTaskMemAlloc
0x14026fc78  nop     dword ptr [rax+rax+00h]
0x14026fc7d  mov     rdx, rax
0x14026fc80  test    rax, rax
0x14026fc83  jnz     short loc_14026FCA1
0x14026fc85  mov     rcx, [rbp+28h]; this
0x14026fc89  mov     r9d, 8007000Eh; char *
0x14026fc8f  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x14026fc96  mov     edx, 5FFh; void *
0x14026fc9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14026fca1  xor     r8d, r8d
0x14026fca4  test    ebx, ebx
0x14026fca6  jnz     short loc_14026FCB0
0x14026fca8  mov     word ptr [rax], 9C43h
0x14026fcad  mov     r8d, edi
0x14026fcb0  xor     r9d, r9d
0x14026fcb3  mov     rax, qword ptr [rbp+var_28+8]
0x14026fcb7  mov     rcx, qword ptr [rbp+var_28]
0x14026fcbb  sub     rax, rcx
0x14026fcbe  sar     rax, 2
0x14026fcc2  test    rax, rax
0x14026fcc5  jz      short loc_14026FCF8
0x14026fcc7  movsxd  rax, dword ptr [rcx+r9*4]
0x14026fccb  lea     r10, qword_140323650
0x14026fcd2  mov     ecx, r8d
0x14026fcd5  movzx   eax, word ptr [r10+rax*2]
0x14026fcda  mov     [rdx+rcx*2], ax
0x14026fcde  add     r8d, edi
0x14026fce1  add     r9, rdi
0x14026fce4  mov     rax, qword ptr [rbp+var_28+8]
0x14026fce8  mov     rcx, qword ptr [rbp+var_28]
0x14026fcec  sub     rax, rcx
0x14026fcef  sar     rax, 2
0x14026fcf3  cmp     r9, rax
0x14026fcf6  jb      short loc_14026FCC7
0x14026fcf8  mov     edi, esi
0x14026fcfa  mov     [r14], edi
0x14026fcfd  mov     [r15], rdx
0x14026fd00  xor     ecx, ecx; pv
0x14026fd02  call    cs:__imp_CoTaskMemFree
0x14026fd09  nop     dword ptr [rax+rax+00h]
0x14026fd0e  nop
0x14026fd0f  mov     rcx, qword ptr [rbp+var_28]
0x14026fd13  test    rcx, rcx
0x14026fd16  jz      short loc_14026FD28
0x14026fd18  mov     rdx, [rbp+var_18]
0x14026fd1c  sub     rdx, rcx
0x14026fd1f  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14026fd23  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14026fd28  mov     rcx, [rbp+var_10]
0x14026fd2c  xor     rcx, rsp; StackCookie
0x14026fd2f  call    __security_check_cookie
0x14026fd34  mov     rbx, [rsp+60h+arg_18]
0x14026fd3c  add     rsp, 60h
0x14026fd40  pop     r15
0x14026fd42  pop     r14
0x14026fd44  pop     rdi
0x14026fd45  pop     rsi
0x14026fd46  pop     rbp
0x14026fd47  retn
```
