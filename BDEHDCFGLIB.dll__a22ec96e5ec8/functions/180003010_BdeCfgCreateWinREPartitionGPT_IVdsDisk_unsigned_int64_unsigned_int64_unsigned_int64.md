# BdeCfgCreateWinREPartitionGPT(IVdsDisk *,unsigned __int64,unsigned __int64,unsigned __int64 *)

- ea: `0x180003010`
- end: `0x18000323a`
- name: `?BdeCfgCreateWinREPartitionGPT@@YAJPEAUIVdsDisk@@_K1PEA_K@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct IVdsDisk *, __int64, unsigned __int64, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180002f54`
- `0x180003010`
- `0x180006b2c`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall BdeCfgCreateWinREPartitionGPT(
        struct IVdsDisk *a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 *a4)
{
  int v8; // ebx
  struct IVdsDiskVtbl *lpVtbl; // rax
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  struct IVdsCreatePartitionEx *v12; // [rsp+48h] [rbp-B8h] BYREF
  struct IVdsAsync *v13; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v14[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _CREATE_PARTITION_PARAMETERS v15; // [rsp+80h] [rbp-80h] BYREF
  struct _VDS_DISK_PROP v16; // [rsp+100h] [rbp+0h] BYREF

  v11 = 0;
  v13 = 0;
  v12 = 0;
  memset(v14, 0, sizeof(v14));
  memset_0(&v15, 0, sizeof(v15));
  memset_0(&v16, 0, sizeof(v16));
  if ( g_pService )
  {
    if ( a1 && a4 )
    {
      v8 = ((__int64 (__fastcall *)(struct IVdsDisk *, struct _VDS_DISK_PROP *))a1->lpVtbl->GetProperties)(a1, &v16);
      if ( v8 >= 0 )
      {
        if ( v16.PartitionStyle == VDS_PST_GPT )
        {
          v15.GptPartInfo.attributes = 0x8000000000000001uLL;
          v15.style = VDS_PST_GPT;
          v15.GptPartInfo.name[0] = 0;
          lpVtbl = a1->lpVtbl;
          v15.GptPartInfo.partitionType = PARTITION_MSFT_RECOVERY_GUID;
          v15.GptPartInfo.partitionId = GUID_00000000_0000_0000_0000_000000000000;
          v8 = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, struct IVdsCreatePartitionEx **))lpVtbl->QueryInterface)(
                 a1,
                 &IID_IVdsCreatePartitionEx,
                 &v12);
          if ( v8 >= 0 )
          {
            v8 = ((__int64 (__fastcall *)(struct IVdsCreatePartitionEx *, __int64, unsigned __int64, _QWORD, struct _CREATE_PARTITION_PARAMETERS *, struct IVdsAsync **))v12->lpVtbl->CreatePartitionEx)(
                   v12,
                   a2,
                   a3,
                   0,
                   &v15,
                   &v13);
            if ( v8 == -2147212273 )
              v8 = BdeCfgCreatePrimaryPartitionAdjustedSize(v12, &v15, &v13, a2, a3, v16.ullSize);
            if ( v8 >= 0 )
            {
              v8 = ((__int64 (__fastcall *)(struct IVdsAsync *, int *, _OWORD *))v13->lpVtbl->Wait)(v13, &v11, v14);
              if ( v8 >= 0 )
              {
                if ( v11 >= 0 )
                  *a4 = *((_QWORD *)&v14[0] + 1);
                else
                  v8 = v11;
              }
            }
          }
        }
        else
        {
          v8 = -1063256037;
        }
      }
    }
    else
    {
      v8 = -2147467261;
    }
    if ( v12 )
    {
      ((void (__fastcall *)(struct IVdsCreatePartitionEx *))v12->lpVtbl->Release)(v12);
      v12 = 0;
    }
    if ( v13 )
    {
      ((void (__fastcall *)(struct IVdsAsync *))v13->lpVtbl->Release)(v13);
      v13 = 0;
    }
  }
  else
  {
    v8 = -1063256042;
  }
  SAFE_FREE_DISKPROP(&v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003010  push    rbp
0x180003012  push    rbx
0x180003013  push    rsi
0x180003014  push    rdi
0x180003015  push    r14
0x180003017  push    r15
0x180003019  lea     rbp, [rsp-98h]
0x180003021  sub     rsp, 198h
0x180003028  mov     rax, cs:__security_cookie
0x18000302f  xor     rax, rsp
0x180003032  mov     [rbp+0C0h+var_40], rax
0x180003039  xorps   xmm0, xmm0
0x18000303c  mov     [rsp+1C0h+var_180], 0
0x180003044  mov     r14, rdx
0x180003047  mov     [rsp+1C0h+var_170], 0
0x180003050  xor     edx, edx; Val
0x180003052  mov     [rsp+1C0h+var_178], 0
0x18000305b  mov     r15, r8
0x18000305e  mov     rdi, rcx
0x180003061  lea     rcx, [rbp+0C0h+var_140]; void *
0x180003065  mov     rsi, r9
0x180003068  movups  [rsp+1C0h+var_168], xmm0
0x18000306d  lea     r8d, [rdx+78h]; Size
0x180003071  movups  [rsp+1C0h+var_158], xmm0
0x180003076  call    memset_0
0x18000307b  xor     edx, edx; Val
0x18000307d  lea     rcx, [rbp+0C0h+var_C0]; void *
0x180003081  mov     r8d, 80h; Size
0x180003087  call    memset_0
0x18000308c  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x180003094  jnz     short loc_1800030A0
0x180003096  mov     ebx, 0C0A00016h
0x18000309b  jmp     loc_180003210
0x1800030a0  test    rdi, rdi
0x1800030a3  jz      loc_1800031CD
0x1800030a9  test    rsi, rsi
0x1800030ac  jz      loc_1800031CD
0x1800030b2  mov     rax, [rdi]
0x1800030b5  lea     rdx, [rbp+0C0h+var_C0]
0x1800030b9  mov     rcx, rdi
0x1800030bc  mov     rax, [rax+18h]
0x1800030c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c5  mov     ebx, eax
0x1800030c7  test    eax, eax
0x1800030c9  js      loc_1800031D2
0x1800030cf  cmp     [rbp+0C0h+var_C0.PartitionStyle], 2
0x1800030d3  jz      short loc_1800030DF
0x1800030d5  mov     ebx, 0C0A0001Bh
0x1800030da  jmp     loc_1800031D2
0x1800030df  movups  xmm0, xmmword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data1
0x1800030e6  mov     rax, 8000000000000001h
0x1800030f0  lea     r8, [rsp+1C0h+var_178]
0x1800030f5  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800030fc  mov     qword ptr [rbp+0C0h+var_140.8+20h], rax
0x180003100  lea     rdx, IID_IVdsCreatePartitionEx
0x180003107  xor     eax, eax
0x180003109  mov     [rbp+0C0h+var_140.style], 2
0x180003110  mov     word ptr [rbp+0C0h+var_140.8+28h], ax
0x180003114  mov     rcx, rdi
0x180003117  mov     rax, [rdi]
0x18000311a  movdqu  xmmword ptr [rbp+0C0h+var_140.8], xmm0
0x18000311f  movdqu  xmmword ptr [rbp+0C0h+var_140.8+10h], xmm1
0x180003124  mov     rax, [rax]
0x180003127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000312c  mov     ebx, eax
0x18000312e  test    eax, eax
0x180003130  js      loc_1800031D2
0x180003136  mov     rcx, [rsp+1C0h+var_178]
0x18000313b  lea     rdx, [rsp+1C0h+var_170]
0x180003140  mov     [rsp+1C0h+var_198], rdx
0x180003145  xor     r9d, r9d
0x180003148  lea     rdx, [rbp+0C0h+var_140]
0x18000314c  mov     r8, r15
0x18000314f  mov     [rsp+1C0h+var_1A0], rdx
0x180003154  mov     rdx, r14
0x180003157  mov     rax, [rcx]
0x18000315a  mov     rax, [rax+18h]
0x18000315e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003163  mov     ebx, eax
0x180003165  cmp     eax, 8004240Fh
0x18000316a  jnz     short loc_180003192
0x18000316c  mov     rax, [rbp+0C0h+var_C0.ullSize]
0x180003170  lea     r8, [rsp+1C0h+var_170]; struct IVdsAsync **
0x180003175  mov     rcx, [rsp+1C0h+var_178]; struct IVdsCreatePartitionEx *
0x18000317a  lea     rdx, [rbp+0C0h+var_140]; struct _CREATE_PARTITION_PARAMETERS *
0x18000317e  mov     [rsp+1C0h+var_198], rax; unsigned __int64
0x180003183  mov     r9, r14; unsigned __int64
0x180003186  mov     [rsp+1C0h+var_1A0], r15; unsigned __int64
0x18000318b  call    ?BdeCfgCreatePrimaryPartitionAdjustedSize@@YAJPEAUIVdsCreatePartitionEx@@PEAU_CREATE_PARTITION_PARAMETERS@@PEAPEAUIVdsAsync@@_K33@Z; BdeCfgCreatePrimaryPartitionAdjustedSize(IVdsCreatePartitionEx *,_CREATE_PARTITION_PARAMETERS *,IVdsAsync * *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180003190  mov     ebx, eax
0x180003192  test    ebx, ebx
0x180003194  js      short loc_1800031D2
0x180003196  mov     rcx, [rsp+1C0h+var_170]
0x18000319b  lea     r8, [rsp+1C0h+var_168]
0x1800031a0  lea     rdx, [rsp+1C0h+var_180]
0x1800031a5  mov     rax, [rcx]
0x1800031a8  mov     rax, [rax+20h]
0x1800031ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b1  mov     ebx, eax
0x1800031b3  test    eax, eax
0x1800031b5  js      short loc_1800031D2
0x1800031b7  mov     eax, [rsp+1C0h+var_180]
0x1800031bb  test    eax, eax
0x1800031bd  jns     short loc_1800031C3
0x1800031bf  mov     ebx, eax
0x1800031c1  jmp     short loc_1800031D2
0x1800031c3  mov     rax, qword ptr [rsp+1C0h+var_168+8]
0x1800031c8  mov     [rsi], rax
0x1800031cb  jmp     short loc_1800031D2
0x1800031cd  mov     ebx, 80004003h
0x1800031d2  mov     rcx, [rsp+1C0h+var_178]
0x1800031d7  test    rcx, rcx
0x1800031da  jz      short loc_1800031F1
0x1800031dc  mov     rax, [rcx]
0x1800031df  mov     rax, [rax+10h]
0x1800031e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e8  mov     [rsp+1C0h+var_178], 0
0x1800031f1  mov     rcx, [rsp+1C0h+var_170]
0x1800031f6  test    rcx, rcx
0x1800031f9  jz      short loc_180003210
0x1800031fb  mov     rax, [rcx]
0x1800031fe  mov     rax, [rax+10h]
0x180003202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003207  mov     [rsp+1C0h+var_170], 0
0x180003210  lea     rcx, [rbp+0C0h+var_C0]; struct _VDS_DISK_PROP *
0x180003214  call    ?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z; SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)
0x180003219  mov     eax, ebx
0x18000321b  mov     rcx, [rbp+0C0h+var_40]
0x180003222  xor     rcx, rsp; StackCookie
0x180003225  call    __security_check_cookie
0x18000322a  add     rsp, 198h
0x180003231  pop     r15
0x180003233  pop     r14
0x180003235  pop     rdi
0x180003236  pop     rsi
0x180003237  pop     rbx
0x180003238  pop     rbp
0x180003239  retn
```
