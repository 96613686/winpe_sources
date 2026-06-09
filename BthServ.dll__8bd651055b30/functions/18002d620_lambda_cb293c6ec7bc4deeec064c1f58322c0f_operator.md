# _lambda_cb293c6ec7bc4deeec064c1f58322c0f_::operator()

- ea: `0x18002d620`
- end: `0x18002d90e`
- name: `_lambda_cb293c6ec7bc4deeec064c1f58322c0f_::operator()`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002c224`

## callees

- `0x1800024ac`
- `0x1800034a0`
- `0x180010cac`
- `0x1800110fc`
- `0x18001140c`
- `0x18002d620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d855`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d6d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d868`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d6d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d868`
- `deviceassociation!DafMemFree` at `0x18002d6b0`
- `deviceassociation!DafMemFree` at `0x18002d838`
- `deviceassociation!DafMemFree` at `0x18002d6b0`
- `deviceassociation!DafMemFree` at `0x18002d838`
- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x18002d812`
- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x18002d812`
- `deviceassociation!DafCloseAssociationContext` at `0x18002d6ce`
- `deviceassociation!DafCloseAssociationContext` at `0x18002d860`
- `deviceassociation!DafCloseAssociationContext` at `0x18002d6ce`
- `deviceassociation!DafCloseAssociationContext` at `0x18002d860`

## string_xrefs

- `0x18002d8fc`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int *__fastcall lambda_cb293c6ec7bc4deeec064c1f58322c0f_::operator()(int **a1, __int64 a2, __int64 a3)
{
  int *v4; // rsi
  char v5; // di
  __int64 v6; // rcx
  __int64 v7; // r14
  DWORD LastError; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  _BYTE *v11; // rcx
  bool v12; // dl
  _UNKNOWN **v13; // rax
  bool v14; // dl
  int *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r14
  DWORD v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  int *result; // rax
  unsigned int v24; // eax
  __int64 *v25; // [rsp+50h] [rbp-30h]
  int v26[2]; // [rsp+58h] [rbp-28h] BYREF
  char v27; // [rsp+60h] [rbp-20h]
  __int64 *v28; // [rsp+68h] [rbp-18h]
  __int64 v29; // [rsp+70h] [rbp-10h]
  char v30; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v4 = *a1;
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 5));
  v6 = *((_QWORD *)v4 + 8);
  *((_QWORD *)v4 + 8) = 0;
  if ( v6 )
    DafMemFree(v6, a2, a3);
  v7 = *((_QWORD *)v4 + 255);
  if ( v7 )
  {
    LastError = GetLastError();
    DafCloseAssociationContext(v7, v9, v10);
    SetLastError(LastError);
  }
  *((_QWORD *)v4 + 255) = 0;
  memset_0(v4 + 38, 0, 0x760u);
  v11 = WPP_GLOBAL_Control;
  v12 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v13 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v11 = WPP_GLOBAL_Control;
    v13 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v14 = v11 != (_BYTE *)&WPP_GLOBAL_Control && v11[25] >= 4u;
  if ( v14 || v13 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v11 + 2), v14, v13 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v11 + 5));
  v15 = *a1;
  v28 = (__int64 *)(*a1 + 510);
  v29 = 0;
  v30 = 1;
  v25 = (__int64 *)(v15 + 16);
  *(_QWORD *)v26 = 0;
  v27 = 1;
  *a1[1] = DafCreateAssociationContextFromOobBlob(&DAF_ProtocolId_BluetoothLE, 71, byte_1800443F0);
  if ( v27 )
  {
    v16 = *(_QWORD *)v26;
    v18 = *v25;
    *v25 = *(_QWORD *)v26;
    if ( v18 )
      DafMemFree(v18, v16, v17);
  }
  if ( v30 )
  {
    v19 = *v28;
    if ( *v28 )
    {
      v20 = GetLastError();
      DafCloseAssociationContext(v19, v21, v22);
      SetLastError(v20);
    }
    *v28 = v29;
  }
  result = a1[1];
  if ( *result < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v5 = 0;
    LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v17, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v24 = wil::verify_hresult<long>((unsigned int)*a1[1], v16, v17);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v24,
      (int)v26);
  }
  return result;
}

```

## disassembly

```asm
0x18002d620  push    rbp
0x18002d622  push    rbx
0x18002d623  push    rsi
0x18002d624  push    rdi
0x18002d625  push    r12
0x18002d627  push    r14
0x18002d629  push    r15
0x18002d62b  mov     rbp, rsp
0x18002d62e  sub     rsp, 80h
0x18002d635  mov     r12, rcx
0x18002d638  mov     rsi, [rcx]
0x18002d63b  lea     r15, WPP_GLOBAL_Control
0x18002d642  mov     dil, 1
0x18002d645  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d64c  cmp     rcx, r15
0x18002d64f  jz      short loc_18002D65C
0x18002d651  cmp     byte ptr [rcx+19h], 5
0x18002d655  jb      short loc_18002D65C
0x18002d657  mov     dl, dil
0x18002d65a  jmp     short loc_18002D65E
0x18002d65c  xor     dl, dl
0x18002d65e  lea     rbx, WPP_RECORDER_INITIALIZED
0x18002d665  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18002d66c  setnz   r8b
0x18002d670  lea     r9, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d677  test    dl, dl
0x18002d679  jnz     short loc_18002D680
0x18002d67b  test    r8b, r8b
0x18002d67e  jz      short loc_18002D69F
0x18002d680  mov     [rsp+80h+var_38], rsi
0x18002d685  mov     [rsp+80h+var_48], r9
0x18002d68a  mov     word ptr [rsp+80h+var_50], 40h ; '@'
0x18002d691  mov     r9, [rcx+28h]
0x18002d695  mov     rcx, [rcx+10h]
0x18002d699  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002d69e  nop
0x18002d69f  mov     rcx, [rsi+40h]
0x18002d6a3  mov     qword ptr [rsi+40h], 0
0x18002d6ab  test    rcx, rcx
0x18002d6ae  jz      short loc_18002D6B7
0x18002d6b0  call    cs:__imp_DafMemFree
0x18002d6b6  nop
0x18002d6b7  mov     r14, [rsi+7F8h]
0x18002d6be  test    r14, r14
0x18002d6c1  jz      short loc_18002D6E4
0x18002d6c3  call    cs:__imp_GetLastError
0x18002d6c9  mov     ebx, eax
0x18002d6cb  mov     rcx, r14
0x18002d6ce  call    cs:__imp_DafCloseAssociationContext
0x18002d6d4  mov     ecx, ebx; dwErrCode
0x18002d6d6  call    cs:__imp_SetLastError
0x18002d6dc  nop
0x18002d6dd  lea     rbx, WPP_RECORDER_INITIALIZED
0x18002d6e4  mov     qword ptr [rsi+7F8h], 0
0x18002d6ef  lea     rcx, [rsi+98h]; void *
0x18002d6f6  xor     edx, edx; Val
0x18002d6f8  mov     r8d, 760h; Size
0x18002d6fe  call    memset_0
0x18002d703  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d70a  cmp     rcx, r15
0x18002d70d  jz      short loc_18002D71A
0x18002d70f  cmp     byte ptr [rcx+19h], 5
0x18002d713  jb      short loc_18002D71A
0x18002d715  mov     dl, dil
0x18002d718  jmp     short loc_18002D71C
0x18002d71a  xor     dl, dl
0x18002d71c  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002d723  cmp     rax, rbx
0x18002d726  setnz   r8b
0x18002d72a  test    dl, dl
0x18002d72c  jnz     short loc_18002D733
0x18002d72e  test    r8b, r8b
0x18002d731  jz      short loc_18002D768
0x18002d733  mov     [rsp+80h+var_38], rsi
0x18002d738  lea     rsi, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d73f  mov     [rsp+80h+var_48], rsi
0x18002d744  mov     word ptr [rsp+80h+var_50], 41h ; 'A'
0x18002d74b  mov     r9, [rcx+28h]
0x18002d74f  mov     rcx, [rcx+10h]
0x18002d753  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002d758  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d75f  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18002d766  jmp     short loc_18002D76F
0x18002d768  lea     rsi, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d76f  cmp     rcx, r15
0x18002d772  jz      short loc_18002D77F
0x18002d774  cmp     byte ptr [rcx+19h], 4
0x18002d778  jb      short loc_18002D77F
0x18002d77a  mov     dl, dil
0x18002d77d  jmp     short loc_18002D781
0x18002d77f  xor     dl, dl
0x18002d781  cmp     rax, rbx
0x18002d784  setnz   r8b
0x18002d788  test    dl, dl
0x18002d78a  jnz     short loc_18002D791
0x18002d78c  test    r8b, r8b
0x18002d78f  jz      short loc_18002D7AA
0x18002d791  mov     [rsp+80h+var_48], rsi
0x18002d796  mov     word ptr [rsp+80h+var_50], 36h ; '6'
0x18002d79d  mov     r9, [rcx+28h]
0x18002d7a1  mov     rcx, [rcx+10h]
0x18002d7a5  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002d7aa  mov     rcx, [r12]
0x18002d7ae  lea     rax, [rcx+7F8h]
0x18002d7b5  mov     [rbp+var_18], rax
0x18002d7b9  mov     [rbp+var_10], 0
0x18002d7c1  mov     [rbp+var_8], dil
0x18002d7c5  lea     rax, [rcx+40h]
0x18002d7c9  mov     [rbp+var_30], rax
0x18002d7cd  mov     qword ptr [rbp+var_28], 0
0x18002d7d5  mov     [rbp+var_20], dil
0x18002d7d9  mov     [rsp+80h+var_48], 0
0x18002d7e2  mov     [rsp+80h+var_50], 0
0x18002d7eb  lea     rax, [rbp+var_10]
0x18002d7ef  mov     [rsp+80h+var_58], rax
0x18002d7f4  lea     rax, [rbp+var_28]
0x18002d7f8  mov     qword ptr [rsp+80h+var_60], rax; int
0x18002d7fd  xor     r9d, r9d
0x18002d800  lea     r8, byte_1800443F0
0x18002d807  lea     edx, [r9+47h]
0x18002d80b  lea     rcx, DAF_ProtocolId_BluetoothLE
0x18002d812  call    cs:__imp_DafCreateAssociationContextFromOobBlob
0x18002d818  mov     rcx, [r12+8]
0x18002d81d  mov     [rcx], eax
0x18002d81f  cmp     [rbp+var_20], 0
0x18002d823  jz      short loc_18002D83F
0x18002d825  mov     rdx, qword ptr [rbp+var_28]
0x18002d829  mov     rax, [rbp+var_30]
0x18002d82d  mov     rcx, [rax]
0x18002d830  mov     [rax], rdx
0x18002d833  test    rcx, rcx
0x18002d836  jz      short loc_18002D83F
0x18002d838  call    cs:__imp_DafMemFree
0x18002d83e  nop
0x18002d83f  cmp     [rbp+var_8], 0
0x18002d843  jz      short loc_18002D880
0x18002d845  mov     r15, [rbp+var_10]
0x18002d849  mov     rsi, [rbp+var_18]
0x18002d84d  mov     r14, [rsi]
0x18002d850  test    r14, r14
0x18002d853  jz      short loc_18002D876
0x18002d855  call    cs:__imp_GetLastError
0x18002d85b  mov     ebx, eax
0x18002d85d  mov     rcx, r14
0x18002d860  call    cs:__imp_DafCloseAssociationContext
0x18002d866  mov     ecx, ebx; dwErrCode
0x18002d868  call    cs:__imp_SetLastError
0x18002d86e  nop
0x18002d86f  lea     rbx, WPP_RECORDER_INITIALIZED
0x18002d876  mov     [rsi], r15
0x18002d879  lea     r15, WPP_GLOBAL_Control
0x18002d880  mov     rax, [r12+8]
0x18002d885  cmp     dword ptr [rax], 0
0x18002d888  jl      short loc_18002D89C
0x18002d88a  add     rsp, 80h
0x18002d891  pop     r15
0x18002d893  pop     r14
0x18002d895  pop     r12
0x18002d897  pop     rdi
0x18002d898  pop     rsi
0x18002d899  pop     rbx
0x18002d89a  pop     rbp
0x18002d89b  retn
0x18002d89c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8a3  cmp     rcx, r15
0x18002d8a6  jz      short loc_18002D8AE
0x18002d8a8  cmp     byte ptr [rcx+19h], 2
0x18002d8ac  jnb     short loc_18002D8B1
0x18002d8ae  xor     dil, dil
0x18002d8b1  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18002d8b8  setnz   r8b
0x18002d8bc  test    dil, dil
0x18002d8bf  jnz     short loc_18002D8C6
0x18002d8c1  test    r8b, r8b
0x18002d8c4  jz      short loc_18002D8E9
0x18002d8c6  lea     rdx, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d8cd  mov     [rsp+80h+var_48], rdx
0x18002d8d2  mov     word ptr [rsp+80h+var_50], 37h ; '7'
0x18002d8d9  mov     r9, [rcx+28h]
0x18002d8dd  mov     dl, dil
0x18002d8e0  mov     rcx, [rcx+10h]
0x18002d8e4  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002d8e9  mov     rcx, [r12+8]
0x18002d8ee  mov     ecx, [rcx]
0x18002d8f0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d8f5  mov     r9d, eax; char *
0x18002d8f8  mov     rcx, [rbp+38h]; this
0x18002d8fc  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002d903  mov     edx, 22Eh; void *
0x18002d908  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
