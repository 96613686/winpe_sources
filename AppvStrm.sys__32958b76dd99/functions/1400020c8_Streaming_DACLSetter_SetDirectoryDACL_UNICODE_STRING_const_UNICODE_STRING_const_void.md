# Streaming::DACLSetter::SetDirectoryDACL(_UNICODE_STRING const &,_UNICODE_STRING const &,void *)

- ea: `0x1400020c8`
- end: `0x140002291`
- name: `?SetDirectoryDACL@DACLSetter@Streaming@@SAJAEBU_UNICODE_STRING@@0PEAX@Z`
- size: `457`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140011384`

## callees

- `0x1400020c8`
- `0x140003158`
- `0x140005ed8`
- `0x1400147fc`
- `0x140014a50`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400020f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400020f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000212f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002279`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000212f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002279`
- `FLTMGR!FltReleaseContext` at `0x140002175`
- `FLTMGR!FltReleaseContext` at `0x140002262`
- `FLTMGR!FltReleaseContext` at `0x140002175`
- `FLTMGR!FltReleaseContext` at `0x140002262`

## string_xrefs

- `0x1400021c8`: `DACLSetter::SetDirectoryDACL() - Streaming Filter failed to set directory DACL to '%s'. Failure status: 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::DACLSetter::SetDirectoryDACL(
        const struct _UNICODE_STRING *a1,
        const struct _UNICODE_STRING *a2,
        const struct _UNICODE_STRING *a3)
{
  int FileFullName; // ebx
  Streaming::InstanceContextFactory *v8; // rcx
  int v9; // edi
  __int64 v10; // rbx
  _QWORD *CurrentActivityID; // rax
  volatile signed __int32 *Buffer; // rbx
  volatile signed __int32 *v13; // rbx
  void *v14; // [rsp+20h] [rbp-58h]
  __int64 v15; // [rsp+20h] [rbp-58h]
  struct _FLT_FILTER *v16; // [rsp+30h] [rbp-48h] BYREF
  volatile signed __int32 *v17; // [rsp+38h] [rbp-40h]
  struct _UNICODE_STRING v18; // [rsp+40h] [rbp-38h] BYREF
  __int64 v19; // [rsp+50h] [rbp-28h] BYREF
  PVOID P; // [rsp+58h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-18h] BYREF
  PFLT_CONTEXT Context; // [rsp+B8h] [rbp+40h] BYREF

  v19 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  Context = 0;
  v16 = 0;
  FileFullName = Streaming::Utils::GetFileFullName(a1, a2, &v19);
  if ( FileFullName < 0 )
  {
LABEL_2:
    if ( P )
      ExFreePoolWithTag(P, 0);
    return (unsigned int)FileFullName;
  }
  v8 = (Streaming::InstanceContextFactory *)*((_QWORD *)Streaming::gStrmFltData + 3);
  v18 = *a1;
  FileFullName = Streaming::InstanceContextFactory::GetContextByVolumeName(
                   v8,
                   &v18,
                   &v16,
                   (struct Streaming::InstanceContext *)&Context);
  if ( FileFullName < 0 )
  {
    if ( Context )
      FltReleaseContext(Context);
    goto LABEL_2;
  }
  v9 = Streaming::FileOperations::SetDirectoryDACL(
         *((Streaming::FileOperations **)Streaming::gStrmFltData + 1),
         v16,
         (struct _FLT_INSTANCE *)&DestinationString,
         a3,
         v14);
  if ( v9 < 0 )
  {
    v10 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&v16, &DestinationString);
    CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(&v18);
    LODWORD(v15) = v9;
    LogWrite(
      1,
      *CurrentActivityID,
      L"DACLSetter::SetDirectoryDACL() - Streaming Filter failed to set directory DACL to '%s'. Failure status: 0x%08X.",
      v10,
      v15);
    Buffer = (volatile signed __int32 *)v18.Buffer;
    if ( v18.Buffer )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v18.Buffer + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 8LL))(Buffer);
        if ( _InterlockedExchangeAdd(Buffer + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Buffer + 16LL))(Buffer);
      }
    }
    v13 = v17;
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
  }
  if ( Context )
    FltReleaseContext(Context);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400020c8  push    rbp
0x1400020ca  push    rbx
0x1400020cb  push    rsi
0x1400020cc  push    rdi
0x1400020cd  mov     rbp, rsp
0x1400020d0  sub     rsp, 78h
0x1400020d4  mov     rbx, rdx
0x1400020d7  mov     [rbp+var_28], 0
0x1400020df  mov     rdi, rcx
0x1400020e2  mov     [rbp+P], 0
0x1400020ea  xor     edx, edx; SourceString
0x1400020ec  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400020f0  mov     rsi, r8
0x1400020f3  call    cs:__imp_RtlInitUnicodeString
0x1400020fa  nop     dword ptr [rax+rax+00h]
0x1400020ff  lea     r8, [rbp+var_28]
0x140002103  mov     [rbp+Context], 0
0x14000210b  mov     rdx, rbx
0x14000210e  mov     [rbp+var_48], 0
0x140002116  mov     rcx, rdi
0x140002119  call    ?GetFileFullName@Utils@Streaming@@YAJAEBU_UNICODE_STRING@@0AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Utils::GetFileFullName(_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x14000211e  mov     ebx, eax
0x140002120  test    eax, eax
0x140002122  jns     short loc_140002142
0x140002124  mov     rcx, [rbp+P]; P
0x140002128  test    rcx, rcx
0x14000212b  jz      short loc_14000213B
0x14000212d  xor     edx, edx; Tag
0x14000212f  call    cs:__imp_ExFreePoolWithTag
0x140002136  nop     dword ptr [rax+rax+00h]
0x14000213b  mov     eax, ebx
0x14000213d  jmp     loc_140002287
0x140002142  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140002149  lea     r9, [rbp+Context]; struct Streaming::InstanceContext *
0x14000214d  movups  xmm0, xmmword ptr [rdi]
0x140002150  lea     r8, [rbp+var_48]; struct _FLT_INSTANCE **
0x140002154  lea     rdx, [rbp+var_38]; struct _UNICODE_STRING
0x140002158  mov     rcx, [rcx+18h]; this
0x14000215c  movdqu  xmmword ptr [rbp+var_38.Length], xmm0
0x140002161  call    ?GetContextByVolumeName@InstanceContextFactory@Streaming@@QEAAJU_UNICODE_STRING@@AEAPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContextByVolumeName(_UNICODE_STRING,_FLT_INSTANCE * &,Streaming::InstanceContext &)
0x140002166  mov     ebx, eax
0x140002168  test    eax, eax
0x14000216a  jns     short loc_140002183
0x14000216c  mov     rcx, [rbp+Context]; Context
0x140002170  test    rcx, rcx
0x140002173  jz      short loc_140002124
0x140002175  call    cs:__imp_FltReleaseContext
0x14000217c  nop     dword ptr [rax+rax+00h]
0x140002181  jmp     short loc_140002124
0x140002183  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x14000218a  lea     r8, [rbp+DestinationString]; struct _FLT_INSTANCE *
0x14000218e  mov     rdx, [rbp+var_48]; struct _FLT_FILTER *
0x140002192  mov     r9, rsi; struct _UNICODE_STRING *
0x140002195  mov     rcx, [rcx+8]; this
0x140002199  call    ?SetDirectoryDACL@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@PEAX@Z; Streaming::FileOperations::SetDirectoryDACL(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,void *)
0x14000219e  mov     edi, eax
0x1400021a0  test    eax, eax
0x1400021a2  jns     loc_140002259
0x1400021a8  lea     rdx, [rbp+DestinationString]
0x1400021ac  lea     rcx, [rbp+var_48]
0x1400021b0  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x1400021b5  lea     rcx, [rbp+var_38]
0x1400021b9  mov     rbx, [rax]
0x1400021bc  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400021c1  mov     r9, rbx
0x1400021c4  mov     [rsp+78h+var_58], edi
0x1400021c8  lea     r8, aDaclsetterSetd; "DACLSetter::SetDirectoryDACL() - Stream"...
0x1400021cf  mov     ecx, 1
0x1400021d4  mov     rdx, [rax]
0x1400021d7  call    LogWrite
0x1400021dc  mov     rbx, [rbp+var_38.Buffer]
0x1400021e0  or      esi, 0FFFFFFFFh
0x1400021e3  test    rbx, rbx
0x1400021e6  jz      short loc_14000221C
0x1400021e8  mov     eax, esi
0x1400021ea  lock xadd [rbx+8], eax
0x1400021ef  add     eax, esi
0x1400021f1  jnz     short loc_14000221C
0x1400021f3  mov     rax, [rbx]
0x1400021f6  mov     rcx, rbx
0x1400021f9  mov     rax, [rax+8]
0x1400021fd  call    _guard_dispatch_icall
0x140002202  mov     eax, esi
0x140002204  lock xadd [rbx+0Ch], eax
0x140002209  add     eax, esi
0x14000220b  jnz     short loc_14000221C
0x14000220d  mov     rax, [rbx]
0x140002210  mov     rcx, rbx
0x140002213  mov     rax, [rax+10h]
0x140002217  call    _guard_dispatch_icall
0x14000221c  mov     rbx, [rbp+var_40]
0x140002220  test    rbx, rbx
0x140002223  jz      short loc_140002259
0x140002225  mov     eax, esi
0x140002227  lock xadd [rbx+8], eax
0x14000222c  add     eax, esi
0x14000222e  jnz     short loc_140002259
0x140002230  mov     rax, [rbx]
0x140002233  mov     rcx, rbx
0x140002236  mov     rax, [rax+8]
0x14000223a  call    _guard_dispatch_icall
0x14000223f  mov     eax, esi
0x140002241  lock xadd [rbx+0Ch], eax
0x140002246  add     eax, esi
0x140002248  jnz     short loc_140002259
0x14000224a  mov     rax, [rbx]
0x14000224d  mov     rcx, rbx
0x140002250  mov     rax, [rax+10h]
0x140002254  call    _guard_dispatch_icall
0x140002259  mov     rcx, [rbp+Context]; Context
0x14000225d  test    rcx, rcx
0x140002260  jz      short loc_14000226E
0x140002262  call    cs:__imp_FltReleaseContext
0x140002269  nop     dword ptr [rax+rax+00h]
0x14000226e  mov     rcx, [rbp+P]; P
0x140002272  test    rcx, rcx
0x140002275  jz      short loc_140002285
0x140002277  xor     edx, edx; Tag
0x140002279  call    cs:__imp_ExFreePoolWithTag
0x140002280  nop     dword ptr [rax+rax+00h]
0x140002285  mov     eax, edi
0x140002287  add     rsp, 78h
0x14000228b  pop     rdi
0x14000228c  pop     rsi
0x14000228d  pop     rbx
0x14000228e  pop     rbp
0x14000228f  retn
```
