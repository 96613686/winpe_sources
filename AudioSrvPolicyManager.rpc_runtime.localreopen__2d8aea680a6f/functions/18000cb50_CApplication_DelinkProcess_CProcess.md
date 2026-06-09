# CApplication::DelinkProcess(CProcess *)

- ea: `0x18000cb50`
- end: `0x18000ccb7`
- name: `?DelinkProcess@CApplication@@QEAAJPEAVCProcess@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(CApplication *this, CApplication **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d328`
- `0x18000d87c`
- `0x18003ac08`

## callees

- `0x18000bde0`
- `0x18000cb50`
- `0x18000cd24`
- `0x18000f5f4`
- `0x18003a5fc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cb70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cb70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc12`

## string_xrefs

- `0x18000cc9b`: `CApplication::DelinkProcess`

## pseudocode

```c
__int64 __fastcall CApplication::DelinkProcess(CApplication *this, CApplication **a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int ApplicationSpecificEndpointInfo; // eax
  struct IApplicationSpecificEndpointInfo *v6; // rbx
  __int64 **v7; // rdx
  __int64 *i; // rcx
  __int64 *v9; // r9
  __int64 v10; // r9
  int v13; // eax
  int v14; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct IApplicationSpecificEndpointInfo *v16; // [rsp+68h] [rbp+10h] BYREF
  char *v17; // [rsp+70h] [rbp+18h]
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+78h] [rbp+20h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v17 = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v18 = v4;
  v16 = 0;
  ApplicationSpecificEndpointInfo = CApplication::GetApplicationSpecificEndpointInfo(
                                      a2[28],
                                      (struct CProcess *)a2,
                                      &v16);
  v6 = v16;
  if ( ApplicationSpecificEndpointInfo >= 0 )
  {
    if ( v16 )
    {
      v13 = (*(__int64 (__fastcall **)(struct IApplicationSpecificEndpointInfo *, _QWORD))(*(_QWORD *)v16 + 72LL))(
              v16,
              *((unsigned int *)a2 + 40));
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x12E,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
          (const char *)(unsigned int)v13,
          v14);
    }
  }
  v7 = (__int64 **)((char *)this + 72);
  for ( i = (__int64 *)*((_QWORD *)this + 9); i; i = (__int64 *)*i )
  {
    if ( (CApplication **)i[2] == a2 )
    {
      v9 = (__int64 *)*i;
      if ( i == *v7 )
        *v7 = v9;
      else
        *(_QWORD *)i[1] = v9;
      v10 = i[1];
      if ( i == *((__int64 **)this + 10) )
        *((_QWORD *)this + 10) = v10;
      else
        *(_QWORD *)(*i + 8) = v10;
      *i = *((_QWORD *)this + 13);
      *((_QWORD *)this + 13) = i;
      if ( (*((_QWORD *)this + 11))-- == 1 )
        ATL::CAtlList<CPickerHostContext *,ATL::CElementTraits<CPickerHostContext *>>::RemoveAll((char *)this + 72);
      break;
    }
  }
  if ( v6 )
    (*(void (__fastcall **)(struct IApplicationSpecificEndpointInfo *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v4 )
    LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x18000cb50  push    rbx
0x18000cb52  push    rsi
0x18000cb53  push    rdi
0x18000cb54  push    r14
0x18000cb56  push    r15
0x18000cb58  sub     rsp, 30h
0x18000cb5c  mov     r14, rdx
0x18000cb5f  mov     r15, rcx
0x18000cb62  xor     esi, esi
0x18000cb64  lea     rdi, [rcx+20h]
0x18000cb68  mov     [rsp+58h+arg_10], rdi
0x18000cb6d  mov     rcx, rdi; lpCriticalSection
0x18000cb70  call    cs:__imp_EnterCriticalSection
0x18000cb76  mov     [rsp+58h+arg_18], rdi
0x18000cb7b  mov     [rsp+58h+arg_8], rsi
0x18000cb80  lea     r8, [rsp+58h+arg_8]; struct IApplicationSpecificEndpointInfo **
0x18000cb85  mov     rdx, r14; struct CProcess *
0x18000cb88  mov     rcx, [r14+0E0h]; this
0x18000cb8f  call    ?GetApplicationSpecificEndpointInfo@CApplication@@QEAAJPEAVCProcess@@PEAPEAUIApplicationSpecificEndpointInfo@@@Z; CApplication::GetApplicationSpecificEndpointInfo(CProcess *,IApplicationSpecificEndpointInfo * *)
0x18000cb94  mov     rbx, [rsp+58h+arg_8]
0x18000cb99  test    eax, eax
0x18000cb9b  jns     loc_18000CC26
0x18000cba1  lea     rdx, [r15+48h]
0x18000cba5  mov     rcx, [rdx]
0x18000cba8  test    rcx, rcx
0x18000cbab  jz      short loc_18000CBF5
0x18000cbad  cmp     [rcx+10h], r14
0x18000cbb1  jnz     loc_18000CC6B
0x18000cbb7  xor     esi, esi
0x18000cbb9  mov     r9, [rcx]
0x18000cbbc  cmp     rcx, [rdx]
0x18000cbbf  jnz     loc_18000CC73
0x18000cbc5  mov     [rdx], r9
0x18000cbc8  mov     r9, [rcx+8]
0x18000cbcc  cmp     rcx, [rdx+8]
0x18000cbd0  jnz     loc_18000CC7F
0x18000cbd6  mov     [rdx+8], r9
0x18000cbda  mov     rax, [rdx+20h]
0x18000cbde  mov     [rcx], rax
0x18000cbe1  mov     [rdx+20h], rcx
0x18000cbe5  sub     qword ptr [rdx+10h], 1
0x18000cbea  jnz     short loc_18000CBF5
0x18000cbec  mov     rcx, rdx
0x18000cbef  call    ?RemoveAll@?$CAtlList@PEAVCPickerHostContext@@V?$CElementTraits@PEAVCPickerHostContext@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CPickerHostContext *,ATL::CElementTraits<CPickerHostContext *>>::RemoveAll(void)
0x18000cbf4  nop
0x18000cbf5  test    rbx, rbx
0x18000cbf8  jz      short loc_18000CC0A
0x18000cbfa  mov     rax, [rbx]
0x18000cbfd  mov     rcx, rbx
0x18000cc00  mov     rax, [rax+10h]
0x18000cc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc09  nop
0x18000cc0a  test    rdi, rdi
0x18000cc0d  jz      short loc_18000CC18
0x18000cc0f  mov     rcx, rdi; lpCriticalSection
0x18000cc12  call    cs:__imp_LeaveCriticalSection
0x18000cc18  mov     eax, esi
0x18000cc1a  add     rsp, 30h
0x18000cc1e  pop     r15
0x18000cc20  pop     r14
0x18000cc22  pop     rdi
0x18000cc23  pop     rsi
0x18000cc24  pop     rbx
0x18000cc25  retn
0x18000cc26  test    rbx, rbx
0x18000cc29  jz      loc_18000CBA1
0x18000cc2f  mov     rax, [rbx]
0x18000cc32  mov     edx, [r14+0A0h]
0x18000cc39  mov     rcx, rbx
0x18000cc3c  mov     rax, [rax+48h]
0x18000cc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc45  mov     rcx, [rsp+58h]; this
0x18000cc4a  test    eax, eax
0x18000cc4c  jns     loc_18000CBA1
0x18000cc52  mov     r9d, eax; char *
0x18000cc55  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x18000cc5c  mov     edx, 12Eh; void *
0x18000cc61  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000cc66  jmp     loc_18000CBA1
0x18000cc6b  mov     rcx, [rcx]
0x18000cc6e  jmp     loc_18000CBA8
0x18000cc73  mov     rax, [rcx+8]
0x18000cc77  mov     [rax], r9
0x18000cc7a  jmp     loc_18000CBC8
0x18000cc7f  mov     rax, [rcx]
0x18000cc82  mov     [rax+8], r9
0x18000cc86  jmp     loc_18000CBDA
0x18000cc8b  mov     esi, [rsp+58h+arg_0]
0x18000cc8f  test    esi, esi
0x18000cc91  jns     short loc_18000CCA7
0x18000cc93  mov     r8d, esi; int
0x18000cc96  mov     edx, 13Bh; int
0x18000cc9b  lea     rcx, aCapplicationDe; "CApplication::DelinkProcess"
0x18000cca2  call    ?AudPolicyLogError@@YAXPEBDHJ@Z; AudPolicyLogError(char const *,int,long)
0x18000cca7  mov     rdi, [rsp+58h+arg_10]
0x18000ccac  mov     rbx, [rsp+58h+arg_8]
0x18000ccb1  jmp     loc_18000CBF5
```
