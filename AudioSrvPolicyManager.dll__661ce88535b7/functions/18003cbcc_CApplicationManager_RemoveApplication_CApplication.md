# CApplicationManager::RemoveApplication(CApplication * &)

- ea: `0x18003cbcc`
- end: `0x18003cca2`
- name: `?RemoveApplication@CApplicationManager@@QEAAJAEAPEAVCApplication@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(CApplicationManager *__hidden this, struct CApplication **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000208c`
- `0x180002ebc`
- `0x18002fc28`

## callees

- `0x18000f4e0`
- `0x18000f5f4`
- `0x180022a14`
- `0x18003cbcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cbf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cbf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cc8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cc8c`

## string_xrefs

- `0x18003cc5a`: `CApplicationManager::RemoveApplication`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CApplicationManager::RemoveApplication(CApplicationManager *this, struct CApplication **a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  struct CApplication **i; // rdx
  struct CApplication ***v6; // r9
  struct CApplication *v7; // rax
  struct CApplication **v8; // rax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  for ( i = (struct CApplication **)*((_QWORD *)this + 9); i; i = (struct CApplication **)*i )
  {
    if ( i[2] == *a2 )
    {
      v6 = (struct CApplication ***)(i + 1);
      v7 = *i;
      if ( i == *((struct CApplication ***)this + 9) )
        *((_QWORD *)this + 9) = v7;
      else
        **v6 = v7;
      v8 = *v6;
      if ( i == *((struct CApplication ***)this + 10) )
        *((_QWORD *)this + 10) = v8;
      else
        *((_QWORD *)*i + 1) = v8;
      ATL::CAtlList<CApplication *,ATL::CElementTraits<CApplication *>>::FreeNode((char *)this + 72);
      break;
    }
  }
  if ( *a2 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    *a2 = 0;
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x18003cbcc  mov     [rsp+arg_18], rbx
0x18003cbd1  mov     [rsp+arg_8], rdx
0x18003cbd6  push    rsi
0x18003cbd7  push    rdi
0x18003cbd8  push    r14
0x18003cbda  sub     rsp, 30h
0x18003cbde  mov     rsi, rdx
0x18003cbe1  mov     rbx, rcx
0x18003cbe4  xor     edi, edi
0x18003cbe6  lea     r14, [rcx+20h]
0x18003cbea  mov     [rsp+48h+arg_10], r14
0x18003cbef  mov     rcx, r14; lpCriticalSection
0x18003cbf2  call    cs:__imp_EnterCriticalSection
0x18003cbf8  mov     rdx, [rbx+48h]
0x18003cbfc  test    rdx, rdx
0x18003cbff  jz      short loc_18003CC70
0x18003cc01  mov     rax, [rsi]
0x18003cc04  cmp     [rdx+10h], rax
0x18003cc08  jz      short loc_18003CC0F
0x18003cc0a  mov     rdx, [rdx]
0x18003cc0d  jmp     short loc_18003CBFC
0x18003cc0f  lea     r9, [rdx+8]
0x18003cc13  mov     rax, [rdx]
0x18003cc16  cmp     rdx, [rbx+48h]
0x18003cc1a  jnz     short loc_18003CC22
0x18003cc1c  mov     [rbx+48h], rax
0x18003cc20  jmp     short loc_18003CC28
0x18003cc22  mov     rcx, [r9]
0x18003cc25  mov     [rcx], rax
0x18003cc28  mov     rax, [r9]
0x18003cc2b  cmp     rdx, [rbx+50h]
0x18003cc2f  jnz     short loc_18003CC37
0x18003cc31  mov     [rbx+50h], rax
0x18003cc35  jmp     short loc_18003CC3E
0x18003cc37  mov     r8, [rdx]
0x18003cc3a  mov     [r8+8], rax
0x18003cc3e  lea     rcx, [rbx+48h]
0x18003cc42  call    ?FreeNode@?$CAtlList@PEAVCApplication@@V?$CElementTraits@PEAVCApplication@@@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<CApplication *,ATL::CElementTraits<CApplication *>>::FreeNode(ATL::CAtlList<CApplication *,ATL::CElementTraits<CApplication *>>::CNode *)
0x18003cc47  nop
0x18003cc48  jmp     short loc_18003CC70
0x18003cc4a  mov     edi, [rsp+48h+arg_0]
0x18003cc4e  test    edi, edi
0x18003cc50  jns     short loc_18003CC66
0x18003cc52  mov     r8d, edi; int
0x18003cc55  mov     edx, 567h; int
0x18003cc5a  lea     rcx, aCapplicationma_3; "CApplicationManager::RemoveApplication"
0x18003cc61  call    ?AudPolicyLogError@@YAXPEBDHJ@Z; AudPolicyLogError(char const *,int,long)
0x18003cc66  mov     r14, [rsp+48h+arg_10]
0x18003cc6b  mov     rsi, [rsp+48h+arg_8]
0x18003cc70  mov     rcx, [rsi]
0x18003cc73  test    rcx, rcx
0x18003cc76  jz      short loc_18003CC84
0x18003cc78  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18003cc7d  mov     qword ptr [rsi], 0
0x18003cc84  test    r14, r14
0x18003cc87  jz      short loc_18003CC92
0x18003cc89  mov     rcx, r14; lpCriticalSection
0x18003cc8c  call    cs:__imp_LeaveCriticalSection
0x18003cc92  mov     eax, edi
0x18003cc94  mov     rbx, [rsp+48h+arg_18]
0x18003cc99  add     rsp, 30h
0x18003cc9d  pop     r14
0x18003cc9f  pop     rdi
0x18003cca0  pop     rsi
0x18003cca1  retn
```
