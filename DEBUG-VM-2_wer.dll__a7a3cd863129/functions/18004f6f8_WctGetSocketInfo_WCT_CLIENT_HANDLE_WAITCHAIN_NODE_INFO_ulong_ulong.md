# WctGetSocketInfo(_WCT_CLIENT_HANDLE *,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18004f6f8`
- end: `0x18004f927`
- name: `?WctGetSocketInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK2@Z`
- size: `559`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x18001c650`
- `0x18001fe24`
- `0x18002cdd0`
- `0x18004f6f8`
- `0x18004f930`
- `0x18005ef84`
- `0x18005f748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f84f`
- `ntdll!RtlNtStatusToDosError` at `0x18004f7a3`
- `ntdll!RtlNtStatusToDosError` at `0x18004f7a3`
- `ntdll!NtQueryInformationThread` at `0x18004f797`
- `ntdll!NtQueryInformationThread` at `0x18004f797`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004f845`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004f845`

## pseudocode

```c
__int64 __fastcall WctGetSocketInfo(HANDLE *a1, struct _WAITCHAIN_NODE_INFO *a2, unsigned int *a3, unsigned int *a4)
{
  unsigned int *v4; // rsi
  unsigned int *v5; // r15
  unsigned __int64 v8; // rdi
  NTSTATUS v9; // eax
  ULONG LastError; // ebx
  int IsWow64; // eax
  const void *v12; // r12
  int v13; // esi
  unsigned __int64 v14; // r15
  __int64 v15; // rax
  _QWORD *v16; // rbx
  unsigned __int64 v17; // rcx
  int v18; // r9d
  unsigned int ReturnLength; // [rsp+20h] [rbp-60h]
  union _SOCKADDR_INET *v21; // [rsp+30h] [rbp-50h]
  union _SOCKADDR_INET *v22; // [rsp+38h] [rbp-48h]
  LPVOID lpBuffer; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v24[8]; // [rsp+48h] [rbp-38h] BYREF
  _OWORD ThreadInformation[3]; // [rsp+50h] [rbp-30h] BYREF
  ULONG v26; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int *v27; // [rsp+D0h] [rbp+50h]
  unsigned int *v28; // [rsp+D8h] [rbp+58h]

  v28 = a4;
  v27 = a3;
  v4 = a4;
  v5 = a3;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  v26 = 0;
  v8 = -1;
  lpBuffer = 0;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  if ( !a1 )
  {
    LastError = 87;
    goto LABEL_23;
  }
  v9 = NtQueryInformationThread(*a1, ThreadBasicInformation, ThreadInformation, 0x30u, &v26);
  if ( v9 )
  {
    LastError = RtlNtStatusToDosError(v9);
    goto LABEL_23;
  }
  if ( !*((_QWORD *)&ThreadInformation[0] + 1) )
  {
    LastError = 13;
    goto LABEL_23;
  }
  IsWow64 = WctIsWow64(a1[1]);
  v12 = (const void *)*((_QWORD *)&ThreadInformation[0] + 1);
  v13 = IsWow64;
  if ( IsWow64 )
    v12 = (const void *)(*((_QWORD *)&ThreadInformation[0] + 1) + 0x2000LL);
  v14 = -(__int64)(IsWow64 != 0) & 0xFFFFFFFFFFFFF7C0uLL;
  v15 = utl::make_unique<unsigned char [0],0>(v24, v14 + 6256);
  utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
    &lpBuffer,
    v15);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v24);
  v16 = lpBuffer;
  if ( !lpBuffer )
  {
    LastError = 8;
LABEL_13:
    v4 = v28;
    v5 = v27;
    goto LABEL_23;
  }
  if ( !ReadProcessMemory(a1[1], v12, lpBuffer, v14 + 6256, 0) )
  {
    LastError = GetLastError();
    goto LABEL_13;
  }
  if ( v13 )
    v17 = *((unsigned int *)v16 + 987);
  else
    v17 = v16[743];
  v4 = v28;
  v5 = v27;
  if ( ((v17 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    LastError = 0;
    v8 = v17;
  }
  else
  {
    LastError = 1168;
  }
LABEL_23:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpBuffer);
  if ( !LastError )
  {
    *v4 = 0;
    *v5 = 0;
    a2->ObjectType = WctSocketIoType;
    a2->ObjectStatus = WctStatusNotOwned;
    if ( WctIsSocketRestorable(
           (struct _WCT_CLIENT_HANDLE *)a1,
           v8,
           &a2->LockObject.Alertable,
           v18,
           ReturnLength,
           a2->LockObject.ObjectName,
           v21,
           v22) )
    {
      a2->LockObject.Alertable = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18004f6f8  mov     [rsp-38h+arg_8], rbx
0x18004f6fd  mov     [rsp-38h+arg_18], r9
0x18004f702  mov     [rsp-38h+arg_10], r8
0x18004f707  push    rbp
0x18004f708  push    rsi
0x18004f709  push    rdi
0x18004f70a  push    r12
0x18004f70c  push    r13
0x18004f70e  push    r14
0x18004f710  push    r15
0x18004f712  mov     rbp, rsp
0x18004f715  sub     rsp, 80h
0x18004f71c  mov     rsi, r9
0x18004f71f  mov     r15, r8
0x18004f722  mov     r13, rdx
0x18004f725  mov     r14, rcx
0x18004f728  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f72f  lea     r12, WPP_GLOBAL_Control
0x18004f736  cmp     rcx, r12
0x18004f739  jz      short loc_18004F756
0x18004f73b  test    byte ptr [rcx+1Ch], 4
0x18004f73f  jz      short loc_18004F756
0x18004f741  mov     rcx, [rcx+10h]
0x18004f745  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18004f74c  mov     edx, 39h ; '9'
0x18004f751  call    WPP_SF_
0x18004f756  xorps   xmm0, xmm0
0x18004f759  mov     [rbp+arg_0], 0
0x18004f760  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004f764  mov     [rbp+lpBuffer], 0
0x18004f76c  movups  [rbp+ThreadInformation], xmm0
0x18004f770  movups  [rbp+var_20], xmm0
0x18004f774  movups  [rbp+var_10], xmm0
0x18004f778  test    r14, r14
0x18004f77b  jz      loc_18004F895
0x18004f781  mov     rcx, [r14]; ThreadHandle
0x18004f784  lea     rax, [rbp+arg_0]
0x18004f788  lea     r9d, [rdi+31h]; ThreadInformationLength
0x18004f78c  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18004f791  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18004f795  xor     edx, edx; ThreadInformationClass
0x18004f797  call    cs:__imp_NtQueryInformationThread
0x18004f79d  test    eax, eax
0x18004f79f  jz      short loc_18004F7B0
0x18004f7a1  mov     ecx, eax; Status
0x18004f7a3  call    cs:__imp_RtlNtStatusToDosError
0x18004f7a9  mov     ebx, eax
0x18004f7ab  jmp     loc_18004F89A
0x18004f7b0  cmp     qword ptr [rbp+ThreadInformation+8], 0
0x18004f7b5  jnz     short loc_18004F7C1
0x18004f7b7  mov     ebx, 0Dh
0x18004f7bc  jmp     loc_18004F89A
0x18004f7c1  mov     rcx, [r14+8]; void *
0x18004f7c5  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x18004f7ca  mov     r12, qword ptr [rbp+ThreadInformation+8]
0x18004f7ce  mov     esi, eax
0x18004f7d0  test    eax, eax
0x18004f7d2  jz      short loc_18004F7DB
0x18004f7d4  add     r12, 2000h
0x18004f7db  neg     eax
0x18004f7dd  lea     rcx, [rbp+var_38]
0x18004f7e1  sbb     r15, r15
0x18004f7e4  and     r15, 0FFFFFFFFFFFFF7C0h
0x18004f7eb  lea     rdx, [r15+1870h]
0x18004f7f2  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18004f7f7  mov     rdx, rax
0x18004f7fa  lea     rcx, [rbp+lpBuffer]
0x18004f7fe  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x18004f803  lea     rcx, [rbp+var_38]; void *
0x18004f807  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18004f80c  mov     rbx, [rbp+lpBuffer]
0x18004f810  test    rbx, rbx
0x18004f813  jnz     short loc_18004F82B
0x18004f815  mov     ebx, 8
0x18004f81a  mov     rsi, [rbp+arg_18]
0x18004f81e  lea     r12, WPP_GLOBAL_Control
0x18004f825  mov     r15, [rbp+arg_10]
0x18004f829  jmp     short loc_18004F89A
0x18004f82b  mov     rcx, [r14+8]; hProcess
0x18004f82f  lea     r9, [r15+1870h]; nSize
0x18004f836  mov     r8, rbx; lpBuffer
0x18004f839  mov     [rsp+80h+ReturnLength], 0; lpNumberOfBytesRead
0x18004f842  mov     rdx, r12; lpBaseAddress
0x18004f845  call    cs:__imp_ReadProcessMemory
0x18004f84b  test    eax, eax
0x18004f84d  jnz     short loc_18004F859
0x18004f84f  call    cs:__imp_GetLastError
0x18004f855  mov     ebx, eax
0x18004f857  jmp     short loc_18004F81A
0x18004f859  test    esi, esi
0x18004f85b  jz      short loc_18004F865
0x18004f85d  mov     ecx, [rbx+0F6Ch]
0x18004f863  jmp     short loc_18004F86C
0x18004f865  mov     rcx, [rbx+1738h]
0x18004f86c  mov     rsi, [rbp+arg_18]
0x18004f870  lea     rax, [rcx+1]
0x18004f874  mov     r15, [rbp+arg_10]
0x18004f878  lea     r12, WPP_GLOBAL_Control
0x18004f87f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004f885  jnz     short loc_18004F88E
0x18004f887  mov     ebx, 490h
0x18004f88c  jmp     short loc_18004F89A
0x18004f88e  xor     ebx, ebx
0x18004f890  mov     rdi, rcx
0x18004f893  jmp     short loc_18004F89A
0x18004f895  mov     ebx, 57h ; 'W'
0x18004f89a  lea     rcx, [rbp+lpBuffer]; void *
0x18004f89e  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18004f8a3  test    ebx, ebx
0x18004f8a5  jnz     short loc_18004F8E0
0x18004f8a7  mov     [rsi], ebx
0x18004f8a9  lea     rax, [r13+8]
0x18004f8ad  mov     [r15], ebx
0x18004f8b0  lea     rsi, [r13+110h]
0x18004f8b7  mov     r8, rsi; int *
0x18004f8ba  mov     dword ptr [r13+0], 0Bh
0x18004f8c2  mov     rdx, rdi; unsigned __int64
0x18004f8c5  mov     dword ptr [r13+4], 7
0x18004f8cd  mov     rcx, r14; struct _WCT_CLIENT_HANDLE *
0x18004f8d0  mov     [rsp+80h+var_58], rax; wchar_t *
0x18004f8d5  call    ?WctIsSocketRestorable@@YAKPEAU_WCT_CLIENT_HANDLE@@_KPEAHHKPEA_WPEAT_SOCKADDR_INET@@4@Z; WctIsSocketRestorable(_WCT_CLIENT_HANDLE *,unsigned __int64,int *,int,ulong,wchar_t *,_SOCKADDR_INET *,_SOCKADDR_INET *)
0x18004f8da  test    eax, eax
0x18004f8dc  jz      short loc_18004F8E0
0x18004f8de  mov     [rsi], ebx
0x18004f8e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f8e7  cmp     rcx, r12
0x18004f8ea  jz      short loc_18004F90A
0x18004f8ec  test    byte ptr [rcx+1Ch], 4
0x18004f8f0  jz      short loc_18004F90A
0x18004f8f2  mov     rcx, [rcx+10h]
0x18004f8f6  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18004f8fd  mov     edx, 3Ah ; ':'
0x18004f902  mov     r9d, ebx
0x18004f905  call    WPP_SF_d
0x18004f90a  mov     eax, ebx
0x18004f90c  mov     rbx, [rsp+80h+arg_8]
0x18004f914  add     rsp, 80h
0x18004f91b  pop     r15
0x18004f91d  pop     r14
0x18004f91f  pop     r13
0x18004f921  pop     r12
0x18004f923  pop     rdi
0x18004f924  pop     rsi
0x18004f925  pop     rbp
0x18004f926  retn
```
