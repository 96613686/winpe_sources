# CChangeApplier::ItemTransferComplete(int,int)

- ea: `0x180040aa4`
- end: `0x180040cd2`
- name: `?ItemTransferComplete@CChangeApplier@@AEAAJHH@Z`
- size: `558`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180041238`
- `0x180041f28`
- `0x180044c80`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180034f40`
- `0x180039948`
- `0x180040aa4`
- `0x180043814`
- `0x180045b10`
- `0x180046780`
- `0x18006d7a4`
- `0x180094010`

## string_xrefs

- `0x180040ae1`: `CChangeApplier::ItemTransferComplete`
- `0x180040ca1`: `CChangeApplier::ItemTransferComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::ItemTransferComplete(CChangeApplier *this, int a2, int a3)
{
  int updated; // ebx
  __int64 v7; // rcx
  unsigned int v8; // ecx
  unsigned int v9; // r9d
  unsigned int v10; // edx
  bool v11; // cf
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  struct CSyncChangeBatchWrapper *v15; // rdx
  int v17; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      285,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::ItemTransferComplete");
  }
  if ( a3 || (updated = CSyncChangeWrapper::SetFilter(*((_QWORD *)this + 68), 0), updated >= 0) )
  {
    if ( !a2 || (updated = CChangeApplier::SaveErrorsForCurrentChange(this, 0), updated >= 0) )
    {
      if ( *((_DWORD *)this + 98) || (updated = CChangeApplier::UpdateSessionStatistics(this), updated >= 0) )
      {
        updated = CChangeApplier::RecordCurrentChangeApplied(this);
        if ( updated >= 0 )
        {
          if ( *((_QWORD *)this + 50) )
          {
            if ( !a3 )
            {
              v7 = *((_QWORD *)this + 68) + 8LL;
              v17 = 0;
              updated = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v7 + 64LL))(v7, &v17);
              if ( updated < 0 )
                goto LABEL_26;
              v8 = *((_DWORD *)this + 118);
              v9 = *((_DWORD *)this + 119);
              v10 = v8 + v17;
              v11 = v8 + v17 < v8;
              v12 = *((_QWORD *)this + 50);
              if ( v11 )
                v10 = -1;
              if ( v10 <= *((_DWORD *)this + 119) )
                v9 = v10;
              *((_DWORD *)this + 118) = v9;
              (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 24LL))(v12, 1, 2);
              goto LABEL_21;
            }
          }
          else if ( !a3 )
          {
LABEL_21:
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 68) + 16LL))(*((_QWORD *)this + 68));
            v13 = *((_QWORD *)this + 69);
            *((_QWORD *)this + 68) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            v14 = *((_QWORD *)this + 73);
            *((_QWORD *)this + 69) = 0;
            if ( v14 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              *((_QWORD *)this + 73) = 0;
            }
          }
          v15 = (struct CSyncChangeBatchWrapper *)*((_QWORD *)this + 62);
          v17 = 0;
          updated = CChangeApplier::BeginItemTransfer(this, v15, 0, a3, &v17);
          if ( updated == 1 && !v17 )
            updated = CChangeApplier::DoBatchKnowledgeProcessing(this);
        }
      }
    }
  }
LABEL_26:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      286,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::ItemTransferComplete",
      updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180040aa4  mov     [rsp+arg_0], rbx
0x180040aa9  mov     [rsp+arg_8], rbp
0x180040aae  push    rsi
0x180040aaf  push    rdi
0x180040ab0  push    r15
0x180040ab2  sub     rsp, 30h
0x180040ab6  mov     esi, r8d
0x180040ab9  mov     ebp, edx
0x180040abb  mov     rdi, rcx
0x180040abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ac5  lea     r15, WPP_GLOBAL_Control
0x180040acc  cmp     rcx, r15
0x180040acf  jz      short loc_180040AF9
0x180040ad1  test    byte ptr [rcx+1Ch], 8
0x180040ad5  jz      short loc_180040AF9
0x180040ad7  cmp     byte ptr [rcx+19h], 5
0x180040adb  jb      short loc_180040AF9
0x180040add  mov     rcx, [rcx+10h]
0x180040ae1  lea     r9, aCchangeapplier_50; "CChangeApplier::ItemTransferComplete"
0x180040ae8  mov     edx, 11Dh
0x180040aed  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180040af4  call    WPP_SF_s
0x180040af9  test    esi, esi
0x180040afb  jnz     short loc_180040B15
0x180040afd  mov     rcx, [rdi+220h]
0x180040b04  xor     edx, edx
0x180040b06  call    ?SetFilter@CSyncChangeWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::SetFilter(SYNC_TRANSFER_FILTER)
0x180040b0b  mov     ebx, eax
0x180040b0d  test    eax, eax
0x180040b0f  js      loc_180040C85
0x180040b15  test    ebp, ebp
0x180040b17  jz      short loc_180040B2D
0x180040b19  xor     edx, edx; int
0x180040b1b  mov     rcx, rdi; this
0x180040b1e  call    ?SaveErrorsForCurrentChange@CChangeApplier@@AEAAJH@Z; CChangeApplier::SaveErrorsForCurrentChange(int)
0x180040b23  mov     ebx, eax
0x180040b25  test    eax, eax
0x180040b27  js      loc_180040C85
0x180040b2d  cmp     dword ptr [rdi+188h], 0
0x180040b34  jnz     short loc_180040B48
0x180040b36  mov     rcx, rdi; this
0x180040b39  call    ?UpdateSessionStatistics@CChangeApplier@@AEAAJXZ; CChangeApplier::UpdateSessionStatistics(void)
0x180040b3e  mov     ebx, eax
0x180040b40  test    eax, eax
0x180040b42  js      loc_180040C85
0x180040b48  mov     rcx, rdi; this
0x180040b4b  call    ?RecordCurrentChangeApplied@CChangeApplier@@AEAAJXZ; CChangeApplier::RecordCurrentChangeApplied(void)
0x180040b50  mov     ebx, eax
0x180040b52  test    eax, eax
0x180040b54  js      loc_180040C85
0x180040b5a  cmp     qword ptr [rdi+190h], 0
0x180040b62  jz      short loc_180040BE3
0x180040b64  test    esi, esi
0x180040b66  jnz     loc_180040C46
0x180040b6c  mov     rcx, [rdi+220h]
0x180040b73  lea     rdx, [rsp+48h+arg_10]
0x180040b78  add     rcx, 8
0x180040b7c  mov     [rsp+48h+arg_10], esi
0x180040b80  mov     rax, [rcx]
0x180040b83  mov     rax, [rax+40h]
0x180040b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b8c  mov     ebx, eax
0x180040b8e  test    eax, eax
0x180040b90  js      loc_180040C85
0x180040b96  mov     ecx, [rdi+1D8h]
0x180040b9c  or      eax, 0FFFFFFFFh
0x180040b9f  mov     r8d, [rdi+1DCh]
0x180040ba6  mov     r9d, r8d
0x180040ba9  mov     edx, [rsp+48h+arg_10]
0x180040bad  add     edx, ecx
0x180040baf  mov     dword ptr [rsp+48h+var_28], r8d
0x180040bb4  cmp     edx, ecx
0x180040bb6  mov     rcx, [rdi+190h]
0x180040bbd  cmovb   edx, eax
0x180040bc0  cmp     edx, r8d
0x180040bc3  lea     r8d, [rsi+2]
0x180040bc7  cmovbe  r9d, edx
0x180040bcb  lea     edx, [rsi+1]
0x180040bce  mov     [rdi+1D8h], r9d
0x180040bd5  mov     rax, [rcx]
0x180040bd8  mov     rax, [rax+18h]
0x180040bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040be1  jmp     short loc_180040BE7
0x180040be3  test    esi, esi
0x180040be5  jnz     short loc_180040C46
0x180040be7  mov     rcx, [rdi+220h]
0x180040bee  mov     rax, [rcx]
0x180040bf1  mov     rax, [rax+10h]
0x180040bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040bfa  mov     rcx, [rdi+228h]
0x180040c01  mov     qword ptr [rdi+220h], 0
0x180040c0c  mov     rax, [rcx]
0x180040c0f  mov     rax, [rax+10h]
0x180040c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c18  mov     rcx, [rdi+248h]
0x180040c1f  mov     qword ptr [rdi+228h], 0
0x180040c2a  test    rcx, rcx
0x180040c2d  jz      short loc_180040C46
0x180040c2f  mov     rax, [rcx]
0x180040c32  mov     rax, [rax+10h]
0x180040c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c3b  mov     qword ptr [rdi+248h], 0
0x180040c46  mov     rdx, [rdi+1F0h]; struct CSyncChangeBatchWrapper *
0x180040c4d  lea     rax, [rsp+48h+arg_10]
0x180040c52  mov     r9d, esi; int
0x180040c55  mov     [rsp+48h+var_28], rax; int *
0x180040c5a  xor     r8d, r8d; int
0x180040c5d  mov     [rsp+48h+arg_10], 0
0x180040c65  mov     rcx, rdi; this
0x180040c68  call    ?BeginItemTransfer@CChangeApplier@@AEAAJPEAVCSyncChangeBatchWrapper@@HHPEAH@Z; CChangeApplier::BeginItemTransfer(CSyncChangeBatchWrapper *,int,int,int *)
0x180040c6d  mov     ebx, eax
0x180040c6f  cmp     eax, 1
0x180040c72  jnz     short loc_180040C85
0x180040c74  cmp     [rsp+48h+arg_10], 0
0x180040c79  jnz     short loc_180040C85
0x180040c7b  mov     rcx, rdi; this
0x180040c7e  call    ?DoBatchKnowledgeProcessing@CChangeApplier@@AEAAJXZ; CChangeApplier::DoBatchKnowledgeProcessing(void)
0x180040c83  mov     ebx, eax
0x180040c85  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c8c  cmp     rcx, r15
0x180040c8f  jz      short loc_180040CBD
0x180040c91  test    byte ptr [rcx+1Ch], 8
0x180040c95  jz      short loc_180040CBD
0x180040c97  cmp     byte ptr [rcx+19h], 5
0x180040c9b  jb      short loc_180040CBD
0x180040c9d  mov     rcx, [rcx+10h]
0x180040ca1  lea     r9, aCchangeapplier_50; "CChangeApplier::ItemTransferComplete"
0x180040ca8  mov     edx, 11Eh
0x180040cad  mov     dword ptr [rsp+48h+var_28], ebx
0x180040cb1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180040cb8  call    WPP_SF_sD
0x180040cbd  mov     rbp, [rsp+48h+arg_8]
0x180040cc2  mov     eax, ebx
0x180040cc4  mov     rbx, [rsp+48h+arg_0]
0x180040cc9  add     rsp, 30h
0x180040ccd  pop     r15
0x180040ccf  pop     rdi
0x180040cd0  pop     rsi
0x180040cd1  retn
```
