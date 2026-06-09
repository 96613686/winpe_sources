# CSyncServices::CreateChangeApplier(_GUID const &,void * *)

- ea: `0x18002b020`
- end: `0x18002b20d`
- name: `?CreateChangeApplier@CSyncServices@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `493`
- prototype: `__int64 __fastcall(CSyncServices *this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002b220`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002b020`
- `0x18002d1c8`
- `0x180035510`
- `0x180046aac`
- `0x180094010`

## string_xrefs

- `0x18002b057`: `CSyncServices::CreateChangeApplier`
- `0x18002b1e4`: `CSyncServices::CreateChangeApplier`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateChangeApplier(CSyncServices *this, const struct _GUID *a2, void **a3)
{
  PVOID *v6; // rcx
  int Parameters; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  IdParameters *v13; // rcx
  ChangeApplicationServices *v14; // rax
  ChangeApplicationServices *v15; // rax
  ChangeApplicationServices *v16; // rsi
  struct _ID_PARAMETERS v18; // [rsp+30h] [rbp-48h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateChangeApplier");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  Parameters = -2147217407;
  if ( *((_QWORD *)this + 6) )
  {
    Parameters = -2147467261;
    if ( a3 )
    {
      *a3 = 0;
      v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISynchronousNotifyingChangeApplier.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISynchronousNotifyingChangeApplier.Data1 )
        v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISynchronousNotifyingChangeApplier.Data4;
      if ( !v8 )
        goto LABEL_27;
      v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IAsynchronousNotifyingChangeApplier.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAsynchronousNotifyingChangeApplier.Data1 )
        v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IAsynchronousNotifyingChangeApplier.Data4;
      if ( !v9 )
        goto LABEL_27;
      v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISynchronousNotifyingChangeApplier2.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISynchronousNotifyingChangeApplier2.Data1 )
        v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISynchronousNotifyingChangeApplier2.Data4;
      if ( v10 )
      {
        v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IChangeApplicationServices.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IChangeApplicationServices.Data1 )
          v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IChangeApplicationServices.Data4;
        if ( v11 )
        {
          Parameters = -2147024809;
          v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_689ad659_426e_4b7d_802f_e04945c71ec3.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_689ad659_426e_4b7d_802f_e04945c71ec3.Data1 )
            v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_689ad659_426e_4b7d_802f_e04945c71ec3.Data4;
          if ( !v12 )
            Parameters = -2147467262;
        }
        else
        {
          v13 = (IdParameters *)*((_QWORD *)this + 6);
          memset(&v18, 0, sizeof(v18));
          Parameters = IdParameters::GetParameters(v13, &v18);
          if ( Parameters >= 0 )
          {
            Parameters = -2147024882;
            v14 = (ChangeApplicationServices *)SeAlloc(0xE8u);
            if ( v14 )
            {
              v15 = ChangeApplicationServices::ChangeApplicationServices(v14, &v18);
              v16 = v15;
              if ( v15 )
              {
                Parameters = (**(__int64 (__fastcall ***)(ChangeApplicationServices *, const struct _GUID *, void **))v15)(
                               v15,
                               a2,
                               a3);
                (*(void (__fastcall **)(ChangeApplicationServices *))(*(_QWORD *)v16 + 16LL))(v16);
              }
            }
          }
        }
      }
      else
      {
LABEL_27:
        Parameters = CChangeApplier_CreateInstance(*((struct IdParameters **)this + 6), a2, a3);
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      17,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateChangeApplier",
      Parameters);
  return (unsigned int)Parameters;
}

```

## disassembly

```asm
0x18002b020  push    rbx
0x18002b022  push    rbp
0x18002b023  push    rsi
0x18002b024  push    rdi
0x18002b025  push    r14
0x18002b027  sub     rsp, 50h
0x18002b02b  mov     r14, r8
0x18002b02e  mov     rdi, rdx
0x18002b031  mov     rsi, rcx
0x18002b034  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b03b  lea     rbp, WPP_GLOBAL_Control
0x18002b042  cmp     rcx, rbp
0x18002b045  jz      short loc_18002B076
0x18002b047  test    byte ptr [rcx+1Ch], 2
0x18002b04b  jz      short loc_18002B076
0x18002b04d  cmp     byte ptr [rcx+19h], 5
0x18002b051  jb      short loc_18002B076
0x18002b053  mov     rcx, [rcx+10h]
0x18002b057  lea     r9, aCsyncservicesC_1; "CSyncServices::CreateChangeApplier"
0x18002b05e  mov     edx, 10h
0x18002b063  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b06a  call    WPP_SF_s
0x18002b06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b076  cmp     qword ptr [rsi+30h], 0
0x18002b07b  mov     ebx, 80041001h
0x18002b080  jz      loc_18002B1CF
0x18002b086  mov     ebx, 80004003h
0x18002b08b  test    r14, r14
0x18002b08e  jz      loc_18002B1CF
0x18002b094  mov     qword ptr [r14], 0
0x18002b09b  mov     rax, [rdi]
0x18002b09e  sub     rax, qword ptr cs:IID_ISynchronousNotifyingChangeApplier.Data1
0x18002b0a5  jnz     short loc_18002B0B2
0x18002b0a7  mov     rax, [rdi+8]
0x18002b0ab  sub     rax, qword ptr cs:IID_ISynchronousNotifyingChangeApplier.Data4
0x18002b0b2  test    rax, rax
0x18002b0b5  jz      loc_18002B1B7
0x18002b0bb  mov     rax, [rdi]
0x18002b0be  sub     rax, qword ptr cs:IID_IAsynchronousNotifyingChangeApplier.Data1
0x18002b0c5  jnz     short loc_18002B0D2
0x18002b0c7  mov     rax, [rdi+8]
0x18002b0cb  sub     rax, qword ptr cs:IID_IAsynchronousNotifyingChangeApplier.Data4
0x18002b0d2  test    rax, rax
0x18002b0d5  jz      loc_18002B1B7
0x18002b0db  mov     rax, [rdi]
0x18002b0de  sub     rax, qword ptr cs:IID_ISynchronousNotifyingChangeApplier2.Data1
0x18002b0e5  jnz     short loc_18002B0F2
0x18002b0e7  mov     rax, [rdi+8]
0x18002b0eb  sub     rax, qword ptr cs:IID_ISynchronousNotifyingChangeApplier2.Data4
0x18002b0f2  test    rax, rax
0x18002b0f5  jz      loc_18002B1B7
0x18002b0fb  mov     rax, [rdi]
0x18002b0fe  sub     rax, qword ptr cs:IID_IChangeApplicationServices.Data1
0x18002b105  jnz     short loc_18002B112
0x18002b107  mov     rax, [rdi+8]
0x18002b10b  sub     rax, qword ptr cs:IID_IChangeApplicationServices.Data4
0x18002b112  test    rax, rax
0x18002b115  jz      short loc_18002B146
0x18002b117  mov     rax, [rdi]
0x18002b11a  mov     ebx, 80070057h
0x18002b11f  sub     rax, qword ptr cs:_GUID_689ad659_426e_4b7d_802f_e04945c71ec3.Data1
0x18002b126  jnz     short loc_18002B133
0x18002b128  mov     rax, [rdi+8]
0x18002b12c  sub     rax, qword ptr cs:_GUID_689ad659_426e_4b7d_802f_e04945c71ec3.Data4
0x18002b133  test    rax, rax
0x18002b136  jnz     loc_18002B1C8
0x18002b13c  mov     ebx, 80004002h
0x18002b141  jmp     loc_18002B1C8
0x18002b146  mov     rcx, [rsi+30h]; this
0x18002b14a  lea     rdx, [rsp+78h+var_48]; struct _ID_PARAMETERS *
0x18002b14f  xorps   xmm0, xmm0
0x18002b152  movups  xmmword ptr [rsp+78h+var_48.dwSize], xmm0
0x18002b157  movups  xmmword ptr [rsp+78h+var_48.itemId.fIsVariable], xmm0
0x18002b15c  call    ?GetParameters@IdParameters@@QEAAJPEAU_ID_PARAMETERS@@@Z; IdParameters::GetParameters(_ID_PARAMETERS *)
0x18002b161  mov     ebx, eax
0x18002b163  test    eax, eax
0x18002b165  js      short loc_18002B1C8
0x18002b167  mov     ecx, 0E8h; unsigned __int64
0x18002b16c  mov     ebx, 8007000Eh
0x18002b171  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002b176  test    rax, rax
0x18002b179  jz      short loc_18002B1C8
0x18002b17b  lea     rdx, [rsp+78h+var_48]; struct _ID_PARAMETERS *
0x18002b180  mov     rcx, rax; this
0x18002b183  call    ??0ChangeApplicationServices@@QEAA@AEBU_ID_PARAMETERS@@@Z; ChangeApplicationServices::ChangeApplicationServices(_ID_PARAMETERS const &)
0x18002b188  mov     rsi, rax
0x18002b18b  test    rax, rax
0x18002b18e  jz      short loc_18002B1C8
0x18002b190  mov     rcx, [rax]
0x18002b193  mov     r8, r14
0x18002b196  mov     rdx, rdi
0x18002b199  mov     rax, [rcx]
0x18002b19c  mov     rcx, rsi
0x18002b19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1a4  mov     rcx, [rsi]
0x18002b1a7  mov     ebx, eax
0x18002b1a9  mov     rax, [rcx+10h]
0x18002b1ad  mov     rcx, rsi
0x18002b1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1b5  jmp     short loc_18002B1C8
0x18002b1b7  mov     rcx, [rsi+30h]; struct IdParameters *
0x18002b1bb  mov     r8, r14; void **
0x18002b1be  mov     rdx, rdi; struct _GUID *
0x18002b1c1  call    ?CChangeApplier_CreateInstance@@YAJPEAVIdParameters@@AEBU_GUID@@PEAPEAX@Z; CChangeApplier_CreateInstance(IdParameters *,_GUID const &,void * *)
0x18002b1c6  mov     ebx, eax
0x18002b1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1cf  cmp     rcx, rbp
0x18002b1d2  jz      short loc_18002B200
0x18002b1d4  test    byte ptr [rcx+1Ch], 2
0x18002b1d8  jz      short loc_18002B200
0x18002b1da  cmp     byte ptr [rcx+19h], 5
0x18002b1de  jb      short loc_18002B200
0x18002b1e0  mov     rcx, [rcx+10h]
0x18002b1e4  lea     r9, aCsyncservicesC_1; "CSyncServices::CreateChangeApplier"
0x18002b1eb  mov     edx, 11h
0x18002b1f0  mov     [rsp+78h+var_58], ebx
0x18002b1f4  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b1fb  call    WPP_SF_sD
0x18002b200  mov     eax, ebx
0x18002b202  add     rsp, 50h
0x18002b206  pop     r14
0x18002b208  pop     rdi
0x18002b209  pop     rsi
0x18002b20a  pop     rbp
0x18002b20b  pop     rbx
0x18002b20c  retn
```
