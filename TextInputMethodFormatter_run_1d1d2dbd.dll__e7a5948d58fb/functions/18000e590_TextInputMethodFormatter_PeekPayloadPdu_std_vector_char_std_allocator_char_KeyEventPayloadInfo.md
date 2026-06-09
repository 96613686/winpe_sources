# TextInputMethodFormatter::PeekPayloadPdu(std::vector<char,std::allocator<char>> &,KeyEventPayloadInfo *)

- ea: `0x18000e590`
- end: `0x18000e65a`
- name: `?PeekPayloadPdu@TextInputMethodFormatter@@QEAAJAEAV?$vector@DV?$allocator@D@std@@@std@@PEAUKeyEventPayloadInfo@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(__int64, void **, __int64, const char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180002db8`
- `0x18000e590`
- `0x180012030`
- `0x180012050`
- `0x18003e324`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000e613`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000e613`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e607`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e607`

## string_xrefs

- `0x18000e631`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000e648`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`

## pseudocode

```c
__int64 __fastcall TextInputMethodFormatter::PeekPayloadPdu(__int64 a1, void **a2, __int64 a3, const char *a4)
{
  PduRecv_ToIRemoteTextInputHost *v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  _OWORD *v11; // rbx
  int v13[3]; // [rsp+20h] [rbp-58h] BYREF
  char v14; // [rsp+2Ch] [rbp-4Ch]
  __int128 v15; // [rsp+30h] [rbp-48h]
  __int128 v16; // [rsp+40h] [rbp-38h]
  __int128 v17; // [rsp+50h] [rbp-28h]
  char v18; // [rsp+60h] [rbp-18h]
  char v19; // [rsp+61h] [rbp-17h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x360,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      a4);
  memset_0(v13, 0, 0x48u);
  v7 = PduRecv_ToIRemoteTextInputHost::Peek_RDPTXT_KEY_EVENT_PAYLOAD_PDU(
         v6,
         *a2,
         (struct Peek_RDPTXT_KEY_EVENT_PAYLOAD_PDU_Data *)v13);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x366,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      (const char *)(unsigned int)v7,
      v13[0]);
  *(_BYTE *)a3 = v18;
  *(_BYTE *)(a3 + 1) = v19;
  *(_BYTE *)(a3 + 2) = v14;
  *(_DWORD *)(a3 + 4) = v13[2];
  v11 = (_OWORD *)(a3 + 8);
  if ( v11 )
  {
    *v11 = v15;
    v11[1] = v16;
    v11[2] = v17;
  }
  else
  {
    *(_DWORD *)_o__errno(v9, v8, v10) = 22;
    _invalid_parameter_noinfo();
  }
  return 0;
}

```

## disassembly

```asm
0x18000e590  mov     [rsp+arg_0], rbx
0x18000e595  push    rdi
0x18000e596  sub     rsp, 70h
0x18000e59a  mov     rbx, r8
0x18000e59d  mov     rdi, rdx
0x18000e5a0  test    r8, r8
0x18000e5a3  jz      loc_18000E643
0x18000e5a9  xor     edx, edx; Val
0x18000e5ab  lea     r8d, [rdx+48h]; Size
0x18000e5af  lea     rcx, [rsp+78h+var_58]; void *
0x18000e5b4  call    memset_0
0x18000e5b9  lea     r8, [rsp+78h+var_58]; struct Peek_RDPTXT_KEY_EVENT_PAYLOAD_PDU_Data *
0x18000e5be  mov     rdx, [rdi]; void *
0x18000e5c1  call    ?Peek_RDPTXT_KEY_EVENT_PAYLOAD_PDU@PduRecv_ToIRemoteTextInputHost@@QEAAJPEAXPEAUPeek_RDPTXT_KEY_EVENT_PAYLOAD_PDU_Data@@@Z; PduRecv_ToIRemoteTextInputHost::Peek_RDPTXT_KEY_EVENT_PAYLOAD_PDU(void *,Peek_RDPTXT_KEY_EVENT_PAYLOAD_PDU_Data *)
0x18000e5c6  test    eax, eax
0x18000e5c8  js      short loc_18000E629
0x18000e5ca  mov     al, [rsp+78h+var_18]
0x18000e5ce  mov     [rbx], al
0x18000e5d0  mov     al, [rsp+78h+var_17]
0x18000e5d4  mov     [rbx+1], al
0x18000e5d7  mov     al, [rsp+78h+var_4C]
0x18000e5db  mov     [rbx+2], al
0x18000e5de  mov     eax, [rsp+78h+var_50]
0x18000e5e2  mov     [rbx+4], eax
0x18000e5e5  add     rbx, 8
0x18000e5e9  jz      short loc_18000E607
0x18000e5eb  movaps  xmm0, [rsp+78h+var_48]
0x18000e5f0  movups  xmmword ptr [rbx], xmm0
0x18000e5f3  movaps  xmm1, [rsp+78h+var_38]
0x18000e5f8  movups  xmmword ptr [rbx+10h], xmm1
0x18000e5fc  movaps  xmm0, [rsp+78h+var_28]
0x18000e601  movups  xmmword ptr [rbx+20h], xmm0
0x18000e605  jmp     short loc_18000E619
0x18000e607  call    cs:__imp__o__errno
0x18000e60d  mov     dword ptr [rax], 16h
0x18000e613  call    cs:__imp__invalid_parameter_noinfo
0x18000e619  xor     eax, eax
0x18000e61b  mov     rbx, [rsp+78h+arg_0]
0x18000e623  add     rsp, 70h
0x18000e627  pop     rdi
0x18000e628  retn
0x18000e629  mov     rcx, [rsp+78h]; this
0x18000e62e  mov     r9d, eax; char *
0x18000e631  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x18000e638  mov     edx, 366h; void *
0x18000e63d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000e643  mov     rcx, [rsp+78h]; this
0x18000e648  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x18000e64f  mov     edx, 360h; void *
0x18000e654  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
