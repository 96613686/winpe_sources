# CSyncServices::CreateSyncChangeHelper(uchar const *,uchar const *,uchar const *,_SYNC_VERSION const *,_SYNC_VERSION const *,ulong,_GUID const &,void * *)

- ea: `0x180028398`
- end: `0x1800285a4`
- name: `?CreateSyncChangeHelper@CSyncServices@@AEAAJPEBE00PEBU_SYNC_VERSION@@1KAEBU_GUID@@PEAPEAX@Z`
- size: `524`
- prototype: `__int64 __fastcall(CSyncServices *this, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const struct _SYNC_VERSION *, const struct _SYNC_VERSION *, unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002c520`
- `0x18002c590`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180028398`
- `0x180055cec`
- `0x180094010`

## string_xrefs

- `0x1800283d8`: `CSyncServices::CreateSyncChangeHelper`
- `0x180028575`: `CSyncServices::CreateSyncChangeHelper`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateSyncChangeHelper(
        CSyncServices *this,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const struct _SYNC_VERSION *a5,
        const struct _SYNC_VERSION *a6,
        unsigned int a7,
        const struct _GUID *a8,
        void **a9)
{
  PVOID *v13; // rcx
  int v14; // edi
  const struct _GUID *v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  struct IdParameters *v19; // rdx
  struct CSyncChange *v20; // rbx
  struct CSyncChange *v22; // [rsp+C0h] [rbp+8h] BYREF

  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateSyncChangeHelper");
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  v14 = -2147217407;
  if ( *((_QWORD *)this + 7) )
  {
    v14 = -2147467261;
    if ( a9 )
    {
      v15 = a8;
      v14 = -2147024809;
      v16 = *(_QWORD *)&a8->Data1 - *(_QWORD *)&IID_ISyncChange.Data1;
      if ( *(_QWORD *)&a8->Data1 == *(_QWORD *)&IID_ISyncChange.Data1 )
        v16 = *(_QWORD *)a8->Data4 - *(_QWORD *)IID_ISyncChange.Data4;
      if ( !v16 )
        goto LABEL_13;
      v17 = *(_QWORD *)&a8->Data1 - *(_QWORD *)&IID_ISyncChangeBuilder.Data1;
      if ( *(_QWORD *)&a8->Data1 == *(_QWORD *)&IID_ISyncChangeBuilder.Data1 )
        v17 = *(_QWORD *)a8->Data4 - *(_QWORD *)IID_ISyncChangeBuilder.Data4;
      if ( !v17 )
      {
LABEL_13:
        v18 = *(_QWORD *)&a8->Data1 - *(_QWORD *)&IID_ISyncChange.Data1;
        if ( *(_QWORD *)&a8->Data1 == *(_QWORD *)&IID_ISyncChange.Data1 )
          v18 = *(_QWORD *)a8->Data4 - *(_QWORD *)IID_ISyncChange.Data4;
        if ( !v18 || (a7 & 3) == 0 )
        {
          v19 = (struct IdParameters *)*((_QWORD *)this + 7);
          v22 = 0;
          v14 = CSyncChange_CreateInstance(0, v19, a2, a4, a5, a6, a3, a7, 0, 0, 0, 0, 0, 0, 0, &v22);
          if ( v14 >= 0 )
          {
            v20 = v22;
            v14 = (**(__int64 (__fastcall ***)(struct CSyncChange *, const struct _GUID *, void **))v22)(v22, v15, a9);
            (*(void (__fastcall **)(struct CSyncChange *))(*(_QWORD *)v20 + 16LL))(v20);
          }
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v13[2],
      51,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateSyncChangeHelper",
      v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180028398  push    rbx
0x18002839a  push    rsi
0x18002839b  push    rdi
0x18002839c  push    r12
0x18002839e  push    r14
0x1800283a0  push    r15
0x1800283a2  sub     rsp, 88h
0x1800283a9  mov     r14, r9
0x1800283ac  mov     r15, r8
0x1800283af  mov     r12, rdx
0x1800283b2  mov     rbx, rcx
0x1800283b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283bc  lea     rax, WPP_GLOBAL_Control
0x1800283c3  cmp     rcx, rax
0x1800283c6  jz      short loc_1800283F7
0x1800283c8  test    byte ptr [rcx+1Ch], 2
0x1800283cc  jz      short loc_1800283F7
0x1800283ce  cmp     byte ptr [rcx+19h], 5
0x1800283d2  jb      short loc_1800283F7
0x1800283d4  mov     rcx, [rcx+10h]
0x1800283d8  lea     r9, aCsyncservicesC_7; "CSyncServices::CreateSyncChangeHelper"
0x1800283df  mov     edx, 32h ; '2'
0x1800283e4  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x1800283eb  call    WPP_SF_s
0x1800283f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283f7  cmp     qword ptr [rbx+38h], 0
0x1800283fc  mov     edi, 80041001h
0x180028401  jz      loc_180028559
0x180028407  cmp     [rsp+0B8h+arg_40], 0
0x180028410  mov     edi, 80004003h
0x180028415  jz      loc_180028559
0x18002841b  mov     rsi, [rsp+0B8h+arg_38]
0x180028423  mov     edi, 80070057h
0x180028428  mov     r8, qword ptr cs:IID_ISyncChange.Data1
0x18002842f  mov     rdx, qword ptr cs:IID_ISyncChange.Data4
0x180028436  mov     rax, [rsi]
0x180028439  sub     rax, r8
0x18002843c  jnz     short loc_180028445
0x18002843e  mov     rax, [rsi+8]
0x180028442  sub     rax, rdx
0x180028445  test    rax, rax
0x180028448  jz      short loc_18002846A
0x18002844a  mov     rax, [rsi]
0x18002844d  sub     rax, qword ptr cs:IID_ISyncChangeBuilder.Data1
0x180028454  jnz     short loc_180028461
0x180028456  mov     rax, [rsi+8]
0x18002845a  sub     rax, qword ptr cs:IID_ISyncChangeBuilder.Data4
0x180028461  test    rax, rax
0x180028464  jnz     loc_180028559
0x18002846a  mov     rax, [rsi]
0x18002846d  sub     rax, r8
0x180028470  jnz     short loc_180028479
0x180028472  mov     rax, [rsi+8]
0x180028476  sub     rax, rdx
0x180028479  mov     r8d, [rsp+0B8h+arg_30]
0x180028481  test    rax, rax
0x180028484  jz      short loc_180028490
0x180028486  test    r8b, 3
0x18002848a  jnz     loc_180028559
0x180028490  mov     rdx, [rbx+38h]; struct IdParameters *
0x180028494  lea     rax, [rsp+0B8h+arg_0]
0x18002849c  mov     [rsp+0B8h+var_40], rax; struct CSyncChange **
0x1800284a1  mov     r9, r14; unsigned __int8 *
0x1800284a4  mov     rax, [rsp+0B8h+arg_28]
0x1800284ac  xor     ecx, ecx; struct ChangeGroup *
0x1800284ae  mov     [rsp+0B8h+var_48], 0; struct ISyncFilterInfo *
0x1800284b7  mov     [rsp+0B8h+var_50], 0; struct ISyncKnowledge *
0x1800284c0  mov     [rsp+0B8h+var_58], 0; struct IForgottenKnowledge *
0x1800284c9  mov     [rsp+0B8h+var_60], 0; struct ISyncKnowledge *
0x1800284d2  mov     [rsp+0B8h+var_68], 0; int
0x1800284da  mov     [rsp+0B8h+var_70], 0; int
0x1800284e2  mov     [rsp+0B8h+var_78], 0; unsigned int
0x1800284ea  mov     [rsp+0B8h+var_80], r8d; unsigned int
0x1800284ef  mov     r8, r12; unsigned __int8 *
0x1800284f2  mov     [rsp+0B8h+var_88], r15; unsigned __int8 *
0x1800284f7  mov     [rsp+0B8h+var_90], rax; struct _SYNC_VERSION *
0x1800284fc  mov     rax, [rsp+0B8h+arg_20]
0x180028504  mov     [rsp+0B8h+var_98], rax; struct _SYNC_VERSION *
0x180028509  mov     [rsp+0B8h+arg_0], 0
0x180028515  call    ?CSyncChange_CreateInstance@@YAJPEAVChangeGroup@@PEAVIdParameters@@PEBE2PEBU_SYNC_VERSION@@32KKHHPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@4PEAUISyncFilterInfo@@PEAPEAVCSyncChange@@@Z; CSyncChange_CreateInstance(ChangeGroup *,IdParameters *,uchar const *,uchar const *,_SYNC_VERSION const *,_SYNC_VERSION const *,uchar const *,ulong,ulong,int,int,ISyncKnowledge *,IForgottenKnowledge *,ISyncKnowledge *,ISyncFilterInfo *,CSyncChange * *)
0x18002851a  mov     edi, eax
0x18002851c  test    eax, eax
0x18002851e  js      short loc_180028552
0x180028520  mov     rbx, [rsp+0B8h+arg_0]
0x180028528  mov     rdx, rsi
0x18002852b  mov     r8, [rsp+0B8h+arg_40]
0x180028533  mov     rcx, rbx
0x180028536  mov     rax, [rbx]
0x180028539  mov     rax, [rax]
0x18002853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028541  mov     edi, eax
0x180028543  mov     rcx, rbx
0x180028546  mov     rax, [rbx]
0x180028549  mov     rax, [rax+10h]
0x18002854d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028552  mov     rcx, cs:WPP_GLOBAL_Control
0x180028559  lea     rax, WPP_GLOBAL_Control
0x180028560  cmp     rcx, rax
0x180028563  jz      short loc_180028591
0x180028565  test    byte ptr [rcx+1Ch], 2
0x180028569  jz      short loc_180028591
0x18002856b  cmp     byte ptr [rcx+19h], 5
0x18002856f  jb      short loc_180028591
0x180028571  mov     rcx, [rcx+10h]
0x180028575  lea     r9, aCsyncservicesC_7; "CSyncServices::CreateSyncChangeHelper"
0x18002857c  mov     edx, 33h ; '3'
0x180028581  mov     dword ptr [rsp+0B8h+var_98], edi
0x180028585  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002858c  call    WPP_SF_sD
0x180028591  mov     eax, edi
0x180028593  add     rsp, 88h
0x18002859a  pop     r15
0x18002859c  pop     r14
0x18002859e  pop     r12
0x1800285a0  pop     rdi
0x1800285a1  pop     rsi
0x1800285a2  pop     rbx
0x1800285a3  retn
```
