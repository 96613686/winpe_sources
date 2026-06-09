# Streaming::StrmPreCreate(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140001aa0`
- end: `0x140001bad`
- name: `?StrmPreCreate@Streaming@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `269`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001aa0`
- `0x140013030`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## string_xrefs

- `0x140001b05`: `Streaming::StrmPreCreate() - Failed in pre-create operation for file %s, error code 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::StrmPreCreate(
        struct _FLT_CALLBACK_DATA *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FILE_OBJECT *a3,
        void **a4)
{
  int v5; // edi
  __int64 v6; // rbx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  void **v11; // [rsp+20h] [rbp-38h]
  _BYTE v12[8]; // [rsp+30h] [rbp-28h] BYREF
  volatile signed __int32 *v13; // [rsp+38h] [rbp-20h]
  _BYTE v14[8]; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v15; // [rsp+48h] [rbp-10h]

  if ( !a3 )
    return 0;
  if ( !this )
    return 0;
  if ( !a2 )
    return 0;
  v5 = Streaming::StrmFltInterface::PreCreate(
         (Streaming::StrmFltInterface *)this,
         (struct _FLT_INSTANCE *)a2,
         a3,
         this,
         (void **)a3);
  if ( v5 >= 0 )
    return 0;
  v6 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v14, a2->IoStatus.Information + 88);
  CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v12);
  LODWORD(v11) = v5;
  LogWrite(
    1,
    *CurrentActivityID,
    L"Streaming::StrmPreCreate() - Failed in pre-create operation for file %s, error code 0x%08X.",
    v6,
    v11);
  v8 = v13;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  v9 = v15;
  if ( v15 && _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return 1;
}

```

## disassembly

```asm
0x140001aa0  mov     [rsp+arg_0], rbx
0x140001aa5  push    rdi
0x140001aa6  sub     rsp, 50h
0x140001aaa  mov     rbx, rdx
0x140001aad  test    r8, r8
0x140001ab0  jz      loc_140001B9F
0x140001ab6  test    rcx, rcx
0x140001ab9  jz      loc_140001B9F
0x140001abf  test    rdx, rdx
0x140001ac2  jz      loc_140001B9F
0x140001ac8  mov     r9, rcx; struct _FLT_CALLBACK_DATA *
0x140001acb  mov     [rsp+58h+var_38], r8; void **
0x140001ad0  call    ?PreCreate@StrmFltInterface@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAPEAX@Z; Streaming::StrmFltInterface::PreCreate(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,void * &)
0x140001ad5  mov     edi, eax
0x140001ad7  test    eax, eax
0x140001ad9  jns     loc_140001B9F
0x140001adf  mov     rdx, [rbx+20h]
0x140001ae3  lea     rcx, [rsp+58h+var_18]
0x140001ae8  add     rdx, 58h ; 'X'
0x140001aec  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140001af1  lea     rcx, [rsp+58h+var_28]
0x140001af6  mov     rbx, [rax]
0x140001af9  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140001afe  mov     r9, rbx
0x140001b01  mov     dword ptr [rsp+58h+var_38], edi
0x140001b05  lea     r8, aStreamingStrmp_0; "Streaming::StrmPreCreate() - Failed in "...
0x140001b0c  mov     ecx, 1
0x140001b11  mov     rdx, [rax]
0x140001b14  call    LogWrite
0x140001b19  mov     rbx, [rsp+58h+var_20]
0x140001b1e  or      edi, 0FFFFFFFFh
0x140001b21  test    rbx, rbx
0x140001b24  jz      short loc_140001B5A
0x140001b26  mov     eax, edi
0x140001b28  lock xadd [rbx+8], eax
0x140001b2d  add     eax, edi
0x140001b2f  jnz     short loc_140001B5A
0x140001b31  mov     rax, [rbx]
0x140001b34  mov     rcx, rbx
0x140001b37  mov     rax, [rax+8]
0x140001b3b  call    _guard_dispatch_icall
0x140001b40  mov     eax, edi
0x140001b42  lock xadd [rbx+0Ch], eax
0x140001b47  add     eax, edi
0x140001b49  jnz     short loc_140001B5A
0x140001b4b  mov     rax, [rbx]
0x140001b4e  mov     rcx, rbx
0x140001b51  mov     rax, [rax+10h]
0x140001b55  call    _guard_dispatch_icall
0x140001b5a  mov     rbx, [rsp+58h+var_10]
0x140001b5f  test    rbx, rbx
0x140001b62  jz      short loc_140001B98
0x140001b64  mov     eax, edi
0x140001b66  lock xadd [rbx+8], eax
0x140001b6b  add     eax, edi
0x140001b6d  jnz     short loc_140001B98
0x140001b6f  mov     rax, [rbx]
0x140001b72  mov     rcx, rbx
0x140001b75  mov     rax, [rax+8]
0x140001b79  call    _guard_dispatch_icall
0x140001b7e  mov     edx, edi
0x140001b80  lock xadd [rbx+0Ch], edx
0x140001b85  add     edx, edi
0x140001b87  jnz     short loc_140001B98
0x140001b89  mov     rdx, [rbx]
0x140001b8c  mov     rcx, rbx
0x140001b8f  mov     rax, [rdx+10h]
0x140001b93  call    _guard_dispatch_icall
0x140001b98  mov     eax, 1
0x140001b9d  jmp     short loc_140001BA1
0x140001b9f  xor     eax, eax
0x140001ba1  mov     rbx, [rsp+58h+arg_0]
0x140001ba6  add     rsp, 50h
0x140001baa  pop     rdi
0x140001bab  retn
```
