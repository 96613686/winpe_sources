# CTieringEngineLib::StartTieringEngine(void *)

- ea: `0x140008e04`
- end: `0x140008fdc`
- name: `?StartTieringEngine@CTieringEngineLib@@QEAAJPEAX@Z`
- size: `472`
- prototype: `__int64 __fastcall(CTieringEngineLib *__hidden this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140004340`

## callees

- `0x14000108c`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140008e04`
- `0x140009f1c`
- `0x14000a700`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008fb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008fb2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140008fa3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140008fa3`

## pseudocode

```c
__int64 __fastcall CTieringEngineLib::StartTieringEngine(CTieringEngineLib *this, void *a2)
{
  PVOID v3; // rdi
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v8[8]; // [rsp+38h] [rbp-41h] BYREF
  int v9; // [rsp+40h] [rbp-39h]
  HANDLE hObject[5]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp-9h] BYREF
  int *v12; // [rsp+90h] [rbp+17h]
  __int64 v13; // [rsp+98h] [rbp+1Fh]

  v3 = TieringEngineLibInstance;
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineLib::StartTieringEngine";
  CHResultImp::CHResultImp((CHResultImp *)v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v3);
  }
  *((_QWORD *)v3 + 26) = a2;
  hObject[0] = 0;
  v4 = EnablePrivilegesInProcess((struct _BACKUP_PRIVILEGE_CONTEXT *)hObject);
  v9 = v4;
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v3);
    }
    if ( (unsigned int)dword_14004C098 > 5
      && (qword_14004C0A8 & 0x200000000000LL) != 0
      && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
    {
      v7 = *((_DWORD *)v3 + 34);
      v13 = 4;
      v12 = &v7;
      tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, byte_140045C11, 0, 0, 3, v11, v7);
    }
    SetThreadpoolWait(*((PTP_WAIT *)v3 + 51), *((HANDLE *)v3 + 26), 0);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
      (unsigned int)v4);
  }
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  CHResultImp::~CHResultImp((CHResultImp *)v8);
  return v5;
}

```

## disassembly

```asm
0x140008e04  push    rbp
0x140008e06  push    rbx
0x140008e07  push    rdi
0x140008e08  push    r14
0x140008e0a  lea     rbp, [rsp-3Fh]
0x140008e0f  sub     rsp, 0B8h
0x140008e16  mov     rax, cs:__security_cookie
0x140008e1d  xor     rax, rsp
0x140008e20  mov     [rbp+57h+var_30], rax
0x140008e24  mov     rax, gs:58h
0x140008e2d  mov     rbx, rdx
0x140008e30  mov     rdi, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x140008e37  mov     edx, 8
0x140008e3c  mov     rcx, [rax]
0x140008e3f  lea     rax, aCtieringengine_11; "CTieringEngineLib::StartTieringEngine"
0x140008e46  mov     [rdx+rcx], rax
0x140008e4a  lea     rcx, [rbp+57h+var_98]; this
0x140008e4e  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140008e53  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e5a  lea     r14, WPP_GLOBAL_Control
0x140008e61  cmp     rcx, r14
0x140008e64  jz      short loc_140008E8A
0x140008e66  test    byte ptr [rcx+1Ch], 1
0x140008e6a  jz      short loc_140008E8A
0x140008e6c  cmp     byte ptr [rcx+19h], 4
0x140008e70  jb      short loc_140008E8A
0x140008e72  mov     rcx, [rcx+10h]
0x140008e76  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140008e7d  mov     edx, 26h ; '&'
0x140008e82  mov     r9, rdi
0x140008e85  call    WPP_SF_q
0x140008e8a  lea     rcx, [rbp+57h+hObject]; struct _BACKUP_PRIVILEGE_CONTEXT *
0x140008e8e  mov     [rdi+0D0h], rbx
0x140008e95  mov     [rbp+57h+hObject], 0
0x140008e9d  call    ?EnablePrivilegesInProcess@@YAJPEAU_BACKUP_PRIVILEGE_CONTEXT@@@Z; EnablePrivilegesInProcess(_BACKUP_PRIVILEGE_CONTEXT *)
0x140008ea2  mov     [rbp+57h+var_90], eax
0x140008ea5  mov     ebx, eax
0x140008ea7  test    eax, eax
0x140008ea9  jns     short loc_140008EEC
0x140008eab  mov     rcx, cs:WPP_GLOBAL_Control
0x140008eb2  cmp     rcx, r14
0x140008eb5  jz      loc_140008FA9
0x140008ebb  test    byte ptr [rcx+1Ch], 1
0x140008ebf  jz      loc_140008FA9
0x140008ec5  cmp     byte ptr [rcx+19h], 2
0x140008ec9  jb      loc_140008FA9
0x140008ecf  mov     rcx, [rcx+10h]
0x140008ed3  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140008eda  mov     edx, 27h ; '''
0x140008edf  mov     r9d, eax
0x140008ee2  call    WPP_SF_d
0x140008ee7  jmp     loc_140008FA9
0x140008eec  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ef3  cmp     rcx, r14
0x140008ef6  jz      short loc_140008F1C
0x140008ef8  test    byte ptr [rcx+1Ch], 1
0x140008efc  jz      short loc_140008F1C
0x140008efe  cmp     byte ptr [rcx+19h], 4
0x140008f02  jb      short loc_140008F1C
0x140008f04  mov     rcx, [rcx+10h]
0x140008f08  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140008f0f  mov     edx, 28h ; '('
0x140008f14  mov     r9, rdi
0x140008f17  call    WPP_SF_q
0x140008f1c  mov     eax, cs:dword_14004C098
0x140008f22  cmp     eax, 5
0x140008f25  jbe     short loc_140008F92
0x140008f27  mov     rcx, cs:qword_14004C0B0
0x140008f2e  mov     rdx, 200000000000h
0x140008f38  mov     rax, cs:qword_14004C0A8
0x140008f3f  test    rdx, rax
0x140008f42  jz      short loc_140008F92
0x140008f44  mov     rax, rcx
0x140008f47  and     rax, rdx
0x140008f4a  cmp     rax, rcx
0x140008f4d  jnz     short loc_140008F92
0x140008f4f  mov     eax, [rdi+88h]
0x140008f55  lea     rdx, byte_140045C11
0x140008f5c  mov     [rbp+57h+var_A0], eax
0x140008f5f  lea     rcx, dword_14004C098
0x140008f66  lea     rax, [rbp+57h+var_A0]
0x140008f6a  mov     [rbp+57h+var_38], 4
0x140008f72  mov     [rbp+57h+var_40], rax
0x140008f76  xor     r9d, r9d
0x140008f79  lea     rax, [rbp+57h+var_60]
0x140008f7d  xor     r8d, r8d
0x140008f80  mov     [rsp+0D0h+var_A8], rax
0x140008f85  mov     [rsp+0D0h+var_B0], 3
0x140008f8d  call    _tlgWriteTransfer_EventWriteTransfer
0x140008f92  mov     rdx, [rdi+0D0h]; h
0x140008f99  xor     r8d, r8d; pftTimeout
0x140008f9c  mov     rcx, [rdi+198h]; pwa
0x140008fa3  call    cs:__imp_SetThreadpoolWait
0x140008fa9  mov     rcx, [rbp+57h+hObject]; hObject
0x140008fad  test    rcx, rcx
0x140008fb0  jz      short loc_140008FB8
0x140008fb2  call    cs:__imp_CloseHandle
0x140008fb8  lea     rcx, [rbp+57h+var_98]; this
0x140008fbc  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140008fc1  mov     eax, ebx
0x140008fc3  mov     rcx, [rbp+57h+var_30]
0x140008fc7  xor     rcx, rsp; StackCookie
0x140008fca  call    __security_check_cookie
0x140008fcf  add     rsp, 0B8h
0x140008fd6  pop     r14
0x140008fd8  pop     rdi
0x140008fd9  pop     rbx
0x140008fda  pop     rbp
0x140008fdb  retn
```
