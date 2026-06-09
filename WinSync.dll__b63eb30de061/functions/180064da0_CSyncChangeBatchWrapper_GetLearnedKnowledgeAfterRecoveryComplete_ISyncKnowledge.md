# CSyncChangeBatchWrapper::GetLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge * *)

- ea: `0x180064da0`
- end: `0x180064e9f`
- name: `?GetLearnedKnowledgeAfterRecoveryComplete@CSyncChangeBatchWrapper@@QEAAJPEAPEAUISyncKnowledge@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CSyncChangeBatchWrapper *__hidden this, struct ISyncKnowledge **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180039948`
- `0x18003a64c`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180064da0`
- `0x180094010`

## string_xrefs

- `0x180064dd2`: `CSyncChangeBatchWrapper::GetLearnedKnowledgeAfterRecoveryComplete`
- `0x180064e78`: `CSyncChangeBatchWrapper::GetLearnedKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatchWrapper::GetLearnedKnowledgeAfterRecoveryComplete(
        CSyncChangeBatchWrapper *this,
        struct ISyncKnowledge **a2)
{
  PVOID *v4; // rcx
  int v5; // ebx
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // r9
  __int64 v8; // [rsp+68h] [rbp+10h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      WPP_238472b3224e399257624831508c69ba_Traceguids,
      "CSyncChangeBatchWrapper::GetLearnedKnowledgeAfterRecoveryComplete");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
    v5 = -2147217379;
    if ( v6 )
    {
      v8 = 0;
      v5 = (**v6)(v6, &GUID_ef64197d_4f44_4ea2_b355_4524713e3bed, &v8);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge **))(*(_QWORD *)v8 + 136LL))(v8, a2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      40,
      (unsigned int)WPP_238472b3224e399257624831508c69ba_Traceguids,
      (unsigned int)"CSyncChangeBatchWrapper::GetLearnedKnowledgeAfterRecoveryComplete",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180064da0  push    rbx
0x180064da2  push    rbp
0x180064da3  push    rsi
0x180064da4  push    rdi
0x180064da5  sub     rsp, 38h
0x180064da9  mov     rdi, rdx
0x180064dac  mov     rsi, rcx
0x180064daf  mov     rcx, cs:WPP_GLOBAL_Control
0x180064db6  lea     rbp, WPP_GLOBAL_Control
0x180064dbd  cmp     rcx, rbp
0x180064dc0  jz      short loc_180064DF1
0x180064dc2  test    byte ptr [rcx+1Ch], 8
0x180064dc6  jz      short loc_180064DF1
0x180064dc8  cmp     byte ptr [rcx+19h], 5
0x180064dcc  jb      short loc_180064DF1
0x180064dce  mov     rcx, [rcx+10h]
0x180064dd2  lea     r9, aCsyncchangebat_17; "CSyncChangeBatchWrapper::GetLearnedKnow"...
0x180064dd9  mov     edx, 27h ; '''
0x180064dde  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180064de5  call    WPP_SF_s
0x180064dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180064df1  mov     ebx, 80004003h
0x180064df6  test    rdi, rdi
0x180064df9  jz      short loc_180064E63
0x180064dfb  mov     r9, [rsi+28h]
0x180064dff  mov     ebx, 8004101Dh
0x180064e04  test    r9, r9
0x180064e07  jz      short loc_180064E63
0x180064e09  mov     [rsp+58h+arg_8], 0
0x180064e12  lea     r8, [rsp+58h+arg_8]
0x180064e17  mov     rax, [r9]
0x180064e1a  lea     rdx, _GUID_ef64197d_4f44_4ea2_b355_4524713e3bed
0x180064e21  mov     rcx, r9
0x180064e24  mov     rax, [rax]
0x180064e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e2c  mov     ebx, eax
0x180064e2e  test    eax, eax
0x180064e30  js      short loc_180064E5C
0x180064e32  mov     rcx, [rsp+58h+arg_8]
0x180064e37  mov     rdx, rdi
0x180064e3a  mov     rax, [rcx]
0x180064e3d  mov     rax, [rax+88h]
0x180064e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e49  mov     rcx, [rsp+58h+arg_8]
0x180064e4e  mov     ebx, eax
0x180064e50  mov     rax, [rcx]
0x180064e53  mov     rax, [rax+10h]
0x180064e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180064e63  cmp     rcx, rbp
0x180064e66  jz      short loc_180064E94
0x180064e68  test    byte ptr [rcx+1Ch], 8
0x180064e6c  jz      short loc_180064E94
0x180064e6e  cmp     byte ptr [rcx+19h], 5
0x180064e72  jb      short loc_180064E94
0x180064e74  mov     rcx, [rcx+10h]
0x180064e78  lea     r9, aCsyncchangebat_17; "CSyncChangeBatchWrapper::GetLearnedKnow"...
0x180064e7f  mov     edx, 28h ; '('
0x180064e84  mov     [rsp+58h+var_38], ebx
0x180064e88  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x180064e8f  call    WPP_SF_sD
0x180064e94  mov     eax, ebx
0x180064e96  add     rsp, 38h
0x180064e9a  pop     rdi
0x180064e9b  pop     rsi
0x180064e9c  pop     rbp
0x180064e9d  pop     rbx
0x180064e9e  retn
```
