# Broker::RpcClientToken::CheckCapability(ulong,int)

- ea: `0x180014618`
- end: `0x180014713`
- name: `?CheckCapability@RpcClientToken@Broker@@QEAA_NKH@Z`
- size: `251`
- prototype: `bool __fastcall(Broker::RpcClientToken *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010560`
- `0x180010e50`

## callees

- `0x180014618`
- `0x18001471c`
- `0x1800147c8`
- `0x18001d9ac`
- `0x1800213b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001468f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001468f`

## pseudocode

```c
bool __fastcall Broker::RpcClientToken::CheckCapability(Broker::RpcClientToken *this, unsigned int a2, int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int16 v11; // bx
  bool v12; // bl
  void **pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int128 v15; // [rsp+38h] [rbp-28h]
  int v16; // [rsp+48h] [rbp-18h]
  int v17; // [rsp+50h] [rbp-10h]
  int v18; // [rsp+80h] [rbp+20h] BYREF
  char v19; // [rsp+90h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+38h] BYREF

  Broker::CoInitWrapper::CoInitWrapper((Broker::CoInitWrapper *)&v19);
  Broker::BackgroundTaskCapabilityWrapper::BackgroundTaskCapabilityWrapper(&ppv);
  v6 = *((_QWORD *)this + 1);
  v18 = 0;
  v7 = *(_QWORD *)ppv;
  if ( a3 )
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, int *))(v7 + 48))(ppv, v6, a2, &v18);
  else
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, int *))(v7 + 24))(ppv, v6, 0, a2, &v18);
  v11 = v8;
  if ( v8 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_ddl(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, a2, v8, a3);
    v15 = 0;
    v16 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v17 = v11;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v12 = v18 != 0;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CoUninitialize();
  return v12;
}

```

## disassembly

```asm
0x180014618  mov     [rsp-18h+arg_8], rbx
0x18001461d  push    rbp
0x18001461e  push    rsi
0x18001461f  push    rdi
0x180014620  mov     rbp, rsp
0x180014623  sub     rsp, 60h
0x180014627  mov     esi, r8d
0x18001462a  mov     edi, edx
0x18001462c  mov     rbx, rcx
0x18001462f  lea     rcx, [rbp+arg_10]; this
0x180014633  call    ??0CoInitWrapper@Broker@@QEAA@XZ; Broker::CoInitWrapper::CoInitWrapper(void)
0x180014638  nop
0x180014639  lea     rcx, [rbp+ppv]; ppv
0x18001463d  call    ??0BackgroundTaskCapabilityWrapper@Broker@@QEAA@XZ; Broker::BackgroundTaskCapabilityWrapper::BackgroundTaskCapabilityWrapper(void)
0x180014642  nop
0x180014643  mov     rdx, [rbx+8]
0x180014647  mov     [rbp+arg_0], 0
0x18001464e  mov     rcx, [rbp+ppv]
0x180014652  mov     rax, [rcx]
0x180014655  test    esi, esi
0x180014657  jnz     short loc_1800146A7
0x180014659  lea     r8, [rbp+arg_0]
0x18001465d  mov     [rsp+60h+var_40], r8
0x180014662  mov     r9d, edi
0x180014665  xor     r8d, r8d
0x180014668  mov     rax, [rax+18h]
0x18001466c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014671  mov     ebx, eax
0x180014673  test    eax, eax
0x180014675  js      short loc_1800146B9
0x180014677  cmp     [rbp+arg_0], 0
0x18001467b  setnz   bl
0x18001467e  mov     rcx, [rbp+ppv]
0x180014682  mov     rdx, [rcx]
0x180014685  mov     rax, [rdx+10h]
0x180014689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001468e  nop
0x18001468f  call    cs:__imp_CoUninitialize
0x180014695  mov     al, bl
0x180014697  mov     rbx, [rsp+60h+arg_8]
0x18001469f  add     rsp, 60h
0x1800146a3  pop     rdi
0x1800146a4  pop     rsi
0x1800146a5  pop     rbp
0x1800146a6  retn
0x1800146a7  lea     r9, [rbp+arg_0]
0x1800146ab  mov     r8d, edi
0x1800146ae  mov     rax, [rax+30h]
0x1800146b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146b7  jmp     short loc_180014671
0x1800146b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146c0  test    dword ptr [rcx+1Ch], 400h
0x1800146c7  jz      short loc_1800146E3
0x1800146c9  cmp     byte ptr [rcx+19h], 2
0x1800146cd  jb      short loc_1800146E3
0x1800146cf  mov     [rsp+60h+var_38], esi
0x1800146d3  mov     dword ptr [rsp+60h+var_40], ebx
0x1800146d7  mov     r9d, edi
0x1800146da  mov     rcx, [rcx+10h]
0x1800146de  call    WPP_SF_ddl
0x1800146e3  xorps   xmm0, xmm0
0x1800146e6  movups  [rbp+var_28], xmm0
0x1800146ea  mov     [rbp+var_18], 1
0x1800146f1  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800146f8  mov     [rbp+pExceptionObject], rax
0x1800146fc  movzx   eax, bx
0x1800146ff  mov     [rbp+var_10], eax
0x180014702  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180014709  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001470d  call    _CxxThrowException_0
```
