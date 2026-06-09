# SetPartitionType(IVdsService *,int,unsigned __int64,_DISKCFG_PARTITION_CUSTOMTYPE,int)

- ea: `0x18005b460`
- end: `0x18005b7ad`
- name: `?SetPartitionType@@YAJPEAUIVdsService@@H_KU_DISKCFG_PARTITION_CUSTOMTYPE@@H@Z`
- size: `845`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18005af10`

## callees

- `0x1800061c0`
- `0x18005b460`
- `0x18005b9d0`
- `0x18005ced6`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18005b6e4`
- `ole32!CoTaskMemFree` at `0x18005b6f7`
- `ole32!CoTaskMemFree` at `0x18005b70a`
- `ole32!CoTaskMemFree` at `0x18005b71d`
- `ole32!CoTaskMemFree` at `0x18005b730`
- `ole32!CoTaskMemFree` at `0x18005b6e4`
- `ole32!CoTaskMemFree` at `0x18005b6f7`
- `ole32!CoTaskMemFree` at `0x18005b70a`
- `ole32!CoTaskMemFree` at `0x18005b71d`
- `ole32!CoTaskMemFree` at `0x18005b730`

## pseudocode

```c
__int64 __fastcall SetPartitionType(struct IVdsService *a1, int a2, __int64 a3, int *a4)
{
  int v8; // edi
  int Disk; // ebx
  _BYTE *v10; // rsi
  __int64 v11; // xmm0_8
  struct IVdsAdvancedDisk2 *v13; // [rsp+30h] [rbp-B1h] BYREF
  struct IVdsAdvancedDisk *v14; // [rsp+38h] [rbp-A9h] BYREF
  _BYTE v15[20]; // [rsp+40h] [rbp-A1h] BYREF
  struct IVdsDisk *v16; // [rsp+58h] [rbp-89h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-81h] BYREF
  int v18; // [rsp+70h] [rbp-71h] BYREF
  _BYTE v19[64]; // [rsp+74h] [rbp-6Dh] BYREF
  int v20; // [rsp+B4h] [rbp-2Dh]
  LPVOID pv; // [rsp+C8h] [rbp-19h]
  LPVOID v22; // [rsp+D0h] [rbp-11h]
  LPVOID v23; // [rsp+D8h] [rbp-9h]
  LPVOID v24; // [rsp+E0h] [rbp-1h]
  LPVOID v25; // [rsp+E8h] [rbp+7h]

  v16 = 0;
  v14 = 0;
  v13 = 0;
  v18 = 0;
  memset_0(v19, 0, 0x7Cu);
  if ( !a1 )
    return 2147942487LL;
  if ( a2 < 0 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v8 = *a4;
  if ( (unsigned int)(*a4 - 1) > 1 )
    return 2147942487LL;
  Disk = GetDisk(a1, a2, &v16, &v14, &v13);
  if ( Disk >= 0 )
  {
    if ( v16 && v14 && v13 )
    {
      Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, int *))v16->lpVtbl->GetProperties)(v16, &v18);
      if ( Disk >= 0 )
      {
        memset(v15, 0, sizeof(v15));
        if ( v8 == 1 )
        {
          if ( v20 == 1 )
          {
            LibLog(
              &g_VdsLibLog,
              0x4000000,
              L"SetPartitionType: The request to set type id and partition specified are both MBR format.");
            v10 = a4 + 1;
            *(_DWORD *)v15 = 1;
            v15[4] = *v10;
LABEL_17:
            Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk2 *, __int64, __int64, _BYTE *))v13->lpVtbl->ChangePartitionType)(
                     v13,
                     a3,
                     1,
                     v15);
            if ( Disk >= 0 && v8 == 2 && !memcmp_0(v10, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) )
            {
              LibLog(
                &g_VdsLibLog,
                0x4000000,
                L"SetPartitionType: This is a recovery partition; setting specific attributes.");
              v17[0] = 2;
              v17[1] = 0x8000000000000001uLL;
              Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, __int64, _QWORD *))v14->lpVtbl->ChangeAttributes)(
                       v14,
                       a3,
                       v17);
            }
            goto LABEL_23;
          }
        }
        else if ( v8 == 2 && v20 == 2 )
        {
          LibLog(
            &g_VdsLibLog,
            0x4000000,
            L"SetPartitionType: The request to set type id and partition specified are both GPT format.");
          v11 = *(_QWORD *)((char *)a4 + 5);
          v10 = a4 + 1;
          *(_DWORD *)v15 = 2;
          *(_QWORD *)&v15[5] = v11;
          v15[4] = *v10;
          *(_DWORD *)&v15[13] = *(_DWORD *)(v10 + 9);
          *(_WORD *)&v15[17] = *(_WORD *)(v10 + 13);
          v15[19] = v10[15];
          goto LABEL_17;
        }
        LibLog(
          &g_VdsLibLog,
          0x2000000,
          L"SetPartitionType: Either the partition style for the request [%s] is either unknown, or does not match the sty"
           "le of the specified partition [%s].");
        Disk = -2147211931;
        LibLog(&g_VdsLibLog, 0x2000000, L"SetPartitionType: ChangePartitionType failed, hr = 0x%x.", 2147755365LL);
      }
    }
    else
    {
      Disk = -2147467259;
    }
  }
LABEL_23:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v22 )
  {
    CoTaskMemFree(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    CoTaskMemFree(v23);
    v23 = 0;
  }
  if ( v24 )
  {
    CoTaskMemFree(v24);
    v24 = 0;
  }
  if ( v25 )
  {
    CoTaskMemFree(v25);
    v25 = 0;
  }
  if ( v13 )
  {
    ((void (__fastcall *)(struct IVdsAdvancedDisk2 *))v13->lpVtbl->Release)(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IVdsAdvancedDisk *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( v16 )
    ((void (__fastcall *)(struct IVdsDisk *))v16->lpVtbl->Release)(v16);
  return (unsigned int)Disk;
}

```

## disassembly

```asm
0x18005b460  push    rbp
0x18005b462  push    rbx
0x18005b463  push    rsi
0x18005b464  push    rdi
0x18005b465  push    r12
0x18005b467  push    r14
0x18005b469  push    r15
0x18005b46b  lea     rbp, [rsp-1Fh]
0x18005b470  sub     rsp, 100h
0x18005b477  mov     rax, cs:__security_cookie
0x18005b47e  xor     rax, rsp
0x18005b481  mov     [rbp+4Fh+var_40], rax
0x18005b485  xor     r12d, r12d
0x18005b488  mov     r15, r8
0x18005b48b  mov     ebx, edx
0x18005b48d  mov     [rsp+130h+var_D8], r12
0x18005b492  mov     r14, rcx
0x18005b495  mov     [rsp+130h+var_F8], r12
0x18005b49a  xor     edx, edx; Val
0x18005b49c  mov     [rsp+130h+var_100], r12
0x18005b4a1  lea     r8d, [r12+7Ch]; Size
0x18005b4a6  mov     [rbp+4Fh+var_C0], r12d
0x18005b4aa  lea     rcx, [rbp+4Fh+var_BC]; void *
0x18005b4ae  mov     rsi, r9
0x18005b4b1  call    memset_0
0x18005b4b6  test    r14, r14
0x18005b4b9  jz      loc_18005B78A
0x18005b4bf  test    ebx, ebx
0x18005b4c1  js      loc_18005B78A
0x18005b4c7  test    r15, r15
0x18005b4ca  jz      loc_18005B78A
0x18005b4d0  mov     edi, [rsi]
0x18005b4d2  lea     eax, [rdi-1]
0x18005b4d5  cmp     eax, 1
0x18005b4d8  ja      loc_18005B78A
0x18005b4de  lea     rax, [rsp+130h+var_100]
0x18005b4e3  mov     edx, ebx; int
0x18005b4e5  lea     r9, [rsp+130h+var_F8]; struct IVdsAdvancedDisk **
0x18005b4ea  mov     [rsp+130h+var_110], rax; struct IVdsAdvancedDisk2 **
0x18005b4ef  lea     r8, [rsp+130h+var_D8]; struct IVdsDisk **
0x18005b4f4  mov     rcx, r14; struct IVdsService *
0x18005b4f7  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x18005b4fc  mov     ebx, eax
0x18005b4fe  test    eax, eax
0x18005b500  js      loc_18005B6DB
0x18005b506  mov     rcx, [rsp+130h+var_D8]
0x18005b50b  test    rcx, rcx
0x18005b50e  jz      loc_18005B6D6
0x18005b514  cmp     [rsp+130h+var_F8], r12
0x18005b519  jz      loc_18005B6D6
0x18005b51f  cmp     [rsp+130h+var_100], r12
0x18005b524  jz      loc_18005B6D6
0x18005b52a  mov     rax, [rcx]
0x18005b52d  lea     rdx, [rbp+4Fh+var_C0]
0x18005b531  mov     rax, [rax+18h]
0x18005b535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b53a  mov     ebx, eax
0x18005b53c  test    eax, eax
0x18005b53e  js      loc_18005B6DB
0x18005b544  xor     eax, eax
0x18005b546  lea     r14d, [r12+2]
0x18005b54b  mov     [rsp+130h+var_E0], eax
0x18005b54f  xorps   xmm0, xmm0
0x18005b552  movups  [rsp+130h+var_F0], xmm0
0x18005b557  cmp     edi, 1
0x18005b55a  jnz     short loc_18005B595
0x18005b55c  cmp     [rbp+4Fh+var_7C], edi
0x18005b55f  jnz     short loc_18005B589
0x18005b561  lea     r8, aSetpartitionty_3; "SetPartitionType: The request to set ty"...
0x18005b568  mov     edx, 4000000h
0x18005b56d  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18005b574  call    LibLog
0x18005b579  add     rsi, 4
0x18005b57d  mov     dword ptr [rsp+130h+var_F0], edi
0x18005b581  mov     al, [rsi]
0x18005b583  mov     byte ptr [rsp+130h+var_F0+4], al
0x18005b587  jmp     short loc_18005B5F1
0x18005b589  lea     r9, aMbr; "MBR"
0x18005b590  jmp     loc_18005B698
0x18005b595  cmp     edi, r14d
0x18005b598  jnz     loc_18005B691
0x18005b59e  cmp     [rbp+4Fh+var_7C], r14d
0x18005b5a2  jnz     loc_18005B688
0x18005b5a8  lea     r8, aSetpartitionty_2; "SetPartitionType: The request to set ty"...
0x18005b5af  mov     edx, 4000000h
0x18005b5b4  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18005b5bb  call    LibLog
0x18005b5c0  movsd   xmm0, qword ptr [rsi+5]
0x18005b5c5  add     rsi, 4
0x18005b5c9  mov     dword ptr [rsp+130h+var_F0], r14d
0x18005b5ce  movsd   qword ptr [rsp+130h+var_F0+5], xmm0
0x18005b5d4  mov     al, [rsi]
0x18005b5d6  mov     byte ptr [rsp+130h+var_F0+4], al
0x18005b5da  mov     eax, [rsi+9]
0x18005b5dd  mov     dword ptr [rsp+130h+var_F0+0Dh], eax
0x18005b5e1  movzx   eax, word ptr [rsi+0Dh]
0x18005b5e5  mov     word ptr [rsp+130h+var_E0+1], ax
0x18005b5ea  mov     al, [rsi+0Fh]
0x18005b5ed  mov     byte ptr [rsp+130h+var_E0+3], al
0x18005b5f1  mov     rcx, [rsp+130h+var_100]
0x18005b5f6  lea     r9, [rsp+130h+var_F0]
0x18005b5fb  mov     r8d, 1
0x18005b601  mov     rdx, r15
0x18005b604  mov     rax, [rcx]
0x18005b607  mov     rax, [rax+18h]
0x18005b60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b610  mov     ebx, eax
0x18005b612  test    eax, eax
0x18005b614  js      loc_18005B6DB
0x18005b61a  cmp     edi, r14d
0x18005b61d  jnz     loc_18005B6DB
0x18005b623  mov     r8d, 10h; Size
0x18005b629  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x18005b630  mov     rcx, rsi; Buf1
0x18005b633  call    memcmp_0
0x18005b638  test    eax, eax
0x18005b63a  jnz     loc_18005B6DB
0x18005b640  lea     r8, aSetpartitionty_0; "SetPartitionType: This is a recovery pa"...
0x18005b647  mov     edx, 4000000h
0x18005b64c  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18005b653  call    LibLog
0x18005b658  mov     rcx, [rsp+130h+var_F8]
0x18005b65d  lea     r8, [rsp+130h+var_D0]
0x18005b662  mov     rax, 8000000000000001h
0x18005b66c  mov     [rsp+130h+var_D0], r14
0x18005b671  mov     [rbp+4Fh+var_C8], rax
0x18005b675  mov     rdx, r15
0x18005b678  mov     rax, [rcx]
0x18005b67b  mov     rax, [rax+38h]
0x18005b67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b684  mov     ebx, eax
0x18005b686  jmp     short loc_18005B6DB
0x18005b688  lea     r9, aGpt; "GPT"
0x18005b68f  jmp     short loc_18005B698
0x18005b691  lea     r9, aUnk; "UNK"
0x18005b698  mov     edi, 2000000h
0x18005b69d  mov     [rsp+130h+var_110], r9
0x18005b6a2  mov     edx, edi
0x18005b6a4  lea     r8, aSetpartitionty; "SetPartitionType: Either the partition "...
0x18005b6ab  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18005b6b2  call    LibLog
0x18005b6b7  mov     ebx, 80042565h
0x18005b6bc  lea     r8, aSetpartitionty_1; "SetPartitionType: ChangePartitionType f"...
0x18005b6c3  mov     r9d, ebx
0x18005b6c6  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18005b6cd  mov     edx, edi
0x18005b6cf  call    LibLog
0x18005b6d4  jmp     short loc_18005B6DB
0x18005b6d6  mov     ebx, 80004005h
0x18005b6db  mov     rcx, [rbp+4Fh+pv]; pv
0x18005b6df  test    rcx, rcx
0x18005b6e2  jz      short loc_18005B6EE
0x18005b6e4  call    cs:__imp_CoTaskMemFree
0x18005b6ea  mov     [rbp+4Fh+pv], r12
0x18005b6ee  mov     rcx, [rbp+4Fh+var_60]; pv
0x18005b6f2  test    rcx, rcx
0x18005b6f5  jz      short loc_18005B701
0x18005b6f7  call    cs:__imp_CoTaskMemFree
0x18005b6fd  mov     [rbp+4Fh+var_60], r12
0x18005b701  mov     rcx, [rbp+4Fh+var_58]; pv
0x18005b705  test    rcx, rcx
0x18005b708  jz      short loc_18005B714
0x18005b70a  call    cs:__imp_CoTaskMemFree
0x18005b710  mov     [rbp+4Fh+var_58], r12
0x18005b714  mov     rcx, [rbp+4Fh+var_50]; pv
0x18005b718  test    rcx, rcx
0x18005b71b  jz      short loc_18005B727
0x18005b71d  call    cs:__imp_CoTaskMemFree
0x18005b723  mov     [rbp+4Fh+var_50], r12
0x18005b727  mov     rcx, [rbp+4Fh+var_48]; pv
0x18005b72b  test    rcx, rcx
0x18005b72e  jz      short loc_18005B73A
0x18005b730  call    cs:__imp_CoTaskMemFree
0x18005b736  mov     [rbp+4Fh+var_48], r12
0x18005b73a  mov     rcx, [rsp+130h+var_100]
0x18005b73f  test    rcx, rcx
0x18005b742  jz      short loc_18005B755
0x18005b744  mov     rax, [rcx]
0x18005b747  mov     rax, [rax+10h]
0x18005b74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b750  mov     [rsp+130h+var_100], r12
0x18005b755  mov     rcx, [rsp+130h+var_F8]
0x18005b75a  test    rcx, rcx
0x18005b75d  jz      short loc_18005B770
0x18005b75f  mov     rax, [rcx]
0x18005b762  mov     rax, [rax+10h]
0x18005b766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b76b  mov     [rsp+130h+var_F8], r12
0x18005b770  mov     rcx, [rsp+130h+var_D8]
0x18005b775  test    rcx, rcx
0x18005b778  jz      short loc_18005B786
0x18005b77a  mov     rax, [rcx]
0x18005b77d  mov     rax, [rax+10h]
0x18005b781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b786  mov     eax, ebx
0x18005b788  jmp     short loc_18005B78F
0x18005b78a  mov     eax, 80070057h
0x18005b78f  mov     rcx, [rbp+4Fh+var_40]
0x18005b793  xor     rcx, rsp; StackCookie
0x18005b796  call    __security_check_cookie
0x18005b79b  add     rsp, 100h
0x18005b7a2  pop     r15
0x18005b7a4  pop     r14
0x18005b7a6  pop     r12
0x18005b7a8  pop     rdi
0x18005b7a9  pop     rsi
0x18005b7aa  pop     rbx
0x18005b7ab  pop     rbp
0x18005b7ac  retn
```
