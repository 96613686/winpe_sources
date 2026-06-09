# FltAddOpenReparseEntry

- ea: `0x180065170`
- end: `0x18006540d`
- name: `FltAddOpenReparseEntry`
- size: `669`
- prototype: `__int64 __fastcall(PVOID FltObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180082400`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180065170`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x1800651e1`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x1800651e1`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18006535c`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18006535c`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18006539b`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18006539b`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1800652ae`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1800652ae`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x180065285`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x180065285`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x180065255`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x180065255`

## pseudocode

```c
__int64 __fastcall FltAddOpenReparseEntry(PVOID FltObject, __int64 a2, _QWORD *a3)
{
  __int64 v4; // r8
  int v7; // edx
  unsigned int v8; // r14d
  __int64 v9; // rdx
  IRP *v10; // rcx
  IRP *v11; // rcx
  unsigned int v12; // ebx
  __int64 *v13; // rax
  __int64 v14; // rcx
  _QWORD *v16; // rax
  char v17; // al
  PVOID EcpContext; // [rsp+68h] [rbp+10h] BYREF
  PECP_LIST EcpList; // [rsp+78h] [rbp+20h] BYREF

  v4 = *(_QWORD *)(a2 + 16);
  EcpList = 0;
  EcpContext = 0;
  v7 = *(unsigned __int8 *)(v4 + 4);
  if ( (_BYTE)v7 && (_BYTE)v7 != 0xF2 && (_BYTE)v7 != 0xF9 )
    return 3221225712LL;
  if ( ((*(_DWORD *)a2 & 1) != 0 && (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(v7 + 22)) & 2) != 0
     || (_BYTE)v7 == 0xF9
     || (_BYTE)v7 == 0xF2)
    && (v7 == 242 || v7 == 249 ? (v11 = *(IRP **)(v4 + 24)) : (v11 = *(IRP **)(a2 - 184)),
        FsRtlGetEcpListFromIrp(v11, &EcpList),
        EcpList) )
  {
    FsRtlFindExtraCreateParameter(EcpList, &ECP_TYPE_OPEN_REPARSE_GUID, &EcpContext, 0);
  }
  else
  {
    v8 = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
    if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1182, 0) < 0 )
      return v8;
    if ( (*(_DWORD *)a2 & 1) != 0
      && (v9 = *(_QWORD *)(a2 + 16),
          (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v9 + 4) + 22)) & 2) != 0)
      || (v9 = *(_QWORD *)(a2 + 16), v17 = *(_BYTE *)(v9 + 4), v17 == -14)
      || v17 == -7 )
    {
      if ( *(unsigned __int8 *)(v9 + 4) == 242 || *(unsigned __int8 *)(v9 + 4) == 249 )
        v10 = *(IRP **)(v9 + 24);
      else
        v10 = *(IRP **)(a2 - 184);
      FsRtlSetEcpListIntoIrp(v10, EcpList);
    }
  }
  if ( !EcpContext )
  {
    v12 = FsRtlAllocateExtraCreateParameterFromLookasideList(
            &ECP_TYPE_OPEN_REPARSE_GUID,
            0x10u,
            0,
            FltMgrOpenReparseEcpCleanup,
            qword_18003F840,
            &EcpContext);
    if ( (int)FltpDbgStatus(v12, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1226, 0) < 0 )
      return v12;
    v16 = EcpContext;
    *((_QWORD *)EcpContext + 1) = EcpContext;
    *v16 = v16;
    FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
  }
  v12 = FltObjectReference(FltObject);
  if ( (int)FltpDbgStatus(v12, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1246, 3223060491LL) < 0 )
    return v12;
  v13 = (__int64 *)EcpContext;
  a3[1] = a3;
  *a3 = a3;
  v14 = *v13;
  if ( *(__int64 **)(*v13 + 8) != v13 )
    __fastfail(3u);
  a3[1] = v13;
  *a3 = v14;
  *(_QWORD *)(v14 + 8) = a3;
  *v13 = (__int64)a3;
  return 0;
}

```

## disassembly

```asm
0x180065170  push    rbx
0x180065172  push    rbp
0x180065173  push    rdi
0x180065174  push    r15
0x180065176  sub     rsp, 38h
0x18006517a  xor     r15d, r15d
0x18006517d  mov     rdi, r8
0x180065180  mov     r8, [rdx+10h]
0x180065184  mov     rbx, rdx
0x180065187  mov     [rsp+58h+EcpList], r15
0x18006518c  mov     rbp, rcx
0x18006518f  mov     [rsp+58h+EcpContext], r15
0x180065194  movzx   edx, byte ptr [r8+4]
0x180065199  test    dl, dl
0x18006519b  jnz     loc_1800653D4
0x1800651a1  mov     eax, [rbx]
0x1800651a3  mov     [rsp+58h+arg_0], rsi
0x1800651a8  lea     rsi, FltpOperationFlags
0x1800651af  mov     [rsp+58h+var_28], r14
0x1800651b4  test    al, 1
0x1800651b6  jz      short loc_1800651C8
0x1800651b8  lea     eax, [rdx+16h]
0x1800651bb  movzx   eax, al
0x1800651be  test    byte ptr [rax+rsi], 2
0x1800651c2  jnz     loc_180065263
0x1800651c8  cmp     dl, 0F9h
0x1800651cb  jz      loc_180065263
0x1800651d1  cmp     dl, 0F2h
0x1800651d4  jz      loc_180065263
0x1800651da  lea     rdx, [rsp+58h+EcpList]; EcpList
0x1800651df  xor     ecx, ecx; Flags
0x1800651e1  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x1800651e8  nop     dword ptr [rax+rax+00h]
0x1800651ed  mov     r8d, 49Eh
0x1800651f3  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x1800651fa  mov     ecx, eax
0x1800651fc  xor     r9d, r9d
0x1800651ff  mov     r14d, eax
0x180065202  call    FltpDbgStatus
0x180065207  test    eax, eax
0x180065209  js      loc_1800653CC
0x18006520f  mov     eax, [rbx]
0x180065211  test    al, 1
0x180065213  jz      loc_1800653F0
0x180065219  mov     rdx, [rbx+10h]
0x18006521d  movzx   eax, byte ptr [rdx+4]
0x180065221  add     al, 16h
0x180065223  movzx   eax, al
0x180065226  test    byte ptr [rax+rsi], 2
0x18006522a  jz      loc_1800653F0
0x180065230  movzx   ecx, byte ptr [rdx+4]
0x180065234  sub     ecx, 0F2h
0x18006523a  jz      loc_1800653C3
0x180065240  cmp     ecx, 7
0x180065243  jz      loc_1800653C3
0x180065249  mov     rcx, [rbx-0B8h]; Irp
0x180065250  mov     rdx, [rsp+58h+EcpList]; EcpList
0x180065255  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x18006525c  nop     dword ptr [rax+rax+00h]
0x180065261  jmp     short loc_1800652BA
0x180065263  mov     eax, edx
0x180065265  sub     eax, 0F2h
0x18006526a  jz      loc_1800653BA
0x180065270  cmp     eax, 7
0x180065273  jz      loc_1800653BA
0x180065279  mov     rcx, [rbx-0B8h]; Irp
0x180065280  lea     rdx, [rsp+58h+EcpList]; EcpList
0x180065285  call    cs:__imp_FsRtlGetEcpListFromIrp
0x18006528c  nop     dword ptr [rax+rax+00h]
0x180065291  mov     rcx, [rsp+58h+EcpList]; EcpList
0x180065296  test    rcx, rcx
0x180065299  jz      loc_1800651DA
0x18006529f  xor     r9d, r9d; EcpContextSize
0x1800652a2  lea     r8, [rsp+58h+EcpContext]; EcpContext
0x1800652a7  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x1800652ae  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1800652b5  nop     dword ptr [rax+rax+00h]
0x1800652ba  cmp     [rsp+58h+EcpContext], r15
0x1800652bf  jz      short loc_180065330
0x1800652c1  mov     rcx, rbp; FltObject
0x1800652c4  call    FltObjectReference
0x1800652c9  mov     r8d, 4DEh
0x1800652cf  mov     [rsp+58h+LookasideList], r15
0x1800652d4  mov     r9d, 0C01C000Bh
0x1800652da  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x1800652e1  mov     ecx, eax
0x1800652e3  mov     ebx, eax
0x1800652e5  call    FltpDbgStatus
0x1800652ea  test    eax, eax
0x1800652ec  js      loc_1800653B3
0x1800652f2  mov     rax, [rsp+58h+EcpContext]
0x1800652f7  mov     [rdi+8], rdi
0x1800652fb  mov     [rdi], rdi
0x1800652fe  mov     rcx, [rax]
0x180065301  cmp     [rcx+8], rax
0x180065305  jnz     loc_1800653AC
0x18006530b  mov     [rdi+8], rax
0x18006530f  mov     [rdi], rcx
0x180065312  mov     [rcx+8], rdi
0x180065316  mov     [rax], rdi
0x180065319  xor     eax, eax
0x18006531b  mov     rsi, [rsp+58h+arg_0]
0x180065320  mov     r14, [rsp+58h+var_28]
0x180065325  add     rsp, 38h
0x180065329  pop     r15
0x18006532b  pop     rdi
0x18006532c  pop     rbp
0x18006532d  pop     rbx
0x18006532e  retn
0x180065330  lea     rax, [rsp+58h+EcpContext]
0x180065335  xor     r8d, r8d; Flags
0x180065338  mov     [rsp+58h+var_30], rax; EcpContext
0x18006533d  lea     r9, FltMgrOpenReparseEcpCleanup; CleanupCallback
0x180065344  lea     rax, qword_18003F840
0x18006534b  mov     edx, 10h; SizeOfContext
0x180065350  lea     rcx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x180065357  mov     [rsp+58h+LookasideList], rax; LookasideList
0x18006535c  call    cs:__imp_FsRtlAllocateExtraCreateParameterFromLookasideList
0x180065363  nop     dword ptr [rax+rax+00h]
0x180065368  mov     r8d, 4CAh
0x18006536e  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x180065375  mov     ecx, eax
0x180065377  xor     r9d, r9d
0x18006537a  mov     ebx, eax
0x18006537c  call    FltpDbgStatus
0x180065381  test    eax, eax
0x180065383  js      short loc_1800653B3
0x180065385  mov     rax, [rsp+58h+EcpContext]
0x18006538a  mov     [rax+8], rax
0x18006538e  mov     [rax], rax
0x180065391  mov     rdx, [rsp+58h+EcpContext]; EcpContext
0x180065396  mov     rcx, [rsp+58h+EcpList]; EcpList
0x18006539b  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1800653a2  nop     dword ptr [rax+rax+00h]
0x1800653a7  jmp     loc_1800652C1
0x1800653ac  mov     ecx, 3
0x1800653b1  int     29h; Win8: RtlFailFast(ecx)
0x1800653b3  mov     eax, ebx
0x1800653b5  jmp     loc_18006531B
0x1800653ba  mov     rcx, [r8+18h]
0x1800653be  jmp     loc_180065280
0x1800653c3  mov     rcx, [rdx+18h]
0x1800653c7  jmp     loc_180065250
0x1800653cc  mov     eax, r14d
0x1800653cf  jmp     loc_18006531B
0x1800653d4  cmp     dl, 0F2h
0x1800653d7  jz      loc_1800651A1
0x1800653dd  cmp     dl, 0F9h
0x1800653e0  jz      loc_1800651A1
0x1800653e6  mov     eax, 0C00000F0h
0x1800653eb  jmp     loc_180065325
0x1800653f0  mov     rdx, [rbx+10h]
0x1800653f4  movzx   eax, byte ptr [rdx+4]
0x1800653f8  cmp     al, 0F2h
0x1800653fa  jz      loc_180065230
0x180065400  cmp     al, 0F9h
0x180065402  jnz     loc_1800652BA
0x180065408  jmp     loc_180065230
```
