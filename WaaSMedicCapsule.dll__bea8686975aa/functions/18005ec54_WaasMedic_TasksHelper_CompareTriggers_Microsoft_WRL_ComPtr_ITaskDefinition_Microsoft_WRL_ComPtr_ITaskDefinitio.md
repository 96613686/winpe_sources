# WaasMedic::TasksHelper::CompareTriggers(Microsoft::WRL::ComPtr<ITaskDefinition>,Microsoft::WRL::ComPtr<ITaskDefinition>,int,bool *)

- ea: `0x18005ec54`
- end: `0x18005f1bf`
- name: `?CompareTriggers@TasksHelper@WaasMedic@@CAJV?$ComPtr@UITaskDefinition@@@WRL@Microsoft@@0HPEA_N@Z`
- size: `1387`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005fc80`

## callees

- `0x18002543c`
- `0x18005ec54`
- `0x180064010`

## string_xrefs

- `0x18005ecf2`: `Failed to get current task triggers! hr = 0x%08x`
- `0x18005ed1d`: `Failed to get expected task trigger count! hr = 0x%08x`
- `0x18005f168`: `Invalid pointer input for TasksHelper::CompareTriggers!`
- `0x18005ecc0`: `Failed to get expected task triggers! hr = 0x%08x`
- `0x18005ef4f`: `Trigger TASK_TRIGGER_TYPE2 did not match! Expected: %d; Actual: %d`
- `0x18005ed40`: `Failed to get current task trigger count! hr = 0x%08x`
- `0x18005f152`: `Error encountered when comparing current task triggers with expected task triggers. hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall WaasMedic::TasksHelper::CompareTriggers(_QWORD *a1, _QWORD *a2, int a3, _BYTE *a4)
{
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // esi
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // r13
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  const wchar_t *v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // [rsp+20h] [rbp-40h] BYREF
  __int64 v43; // [rsp+28h] [rbp-38h] BYREF
  __int16 v44[2]; // [rsp+30h] [rbp-30h] BYREF
  int v45; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v46; // [rsp+38h] [rbp-28h] BYREF
  int v47; // [rsp+3Ch] [rbp-24h] BYREF
  int v48; // [rsp+40h] [rbp-20h] BYREF
  __int64 v49; // [rsp+48h] [rbp-18h] BYREF
  __int64 v50; // [rsp+50h] [rbp-10h] BYREF
  int v51; // [rsp+B0h] [rbp+50h] BYREF

  v51 = a3;
  if ( *a1 && *a2 && a4 )
  {
    *a4 = 0;
    v50 = 0;
    v49 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 72LL))(*a1, &v50);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 72LL))(*a2, &v49);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v46 = 0;
        v45 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 56LL))(v50, &v46);
        v8 = v10;
        if ( v10 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 56LL))(v49, &v45);
          v8 = v11;
          if ( v11 >= 0 )
          {
            if ( v46 == v45 )
            {
              v12 = 1;
              if ( v45 >= 1 )
              {
                while ( 1 )
                {
                  v43 = 0;
                  v42 = 0;
                  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 64LL))(v49, v12, &v43);
                  if ( v8 < 0 )
                    break;
                  v13 = v50;
                  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v50 + 64LL);
                  v15 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                  }
                  v8 = v14(v13, v12, &v42);
                  if ( v8 < 0 )
                  {
                    v36 = v42;
                    if ( v42 )
                    {
                      v42 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                    }
                    v37 = v43;
                    if ( v43 )
                    {
                      v43 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                    }
                    goto LABEL_81;
                  }
                  LOWORD(v51) = -1;
                  v44[0] = -1;
                  v8 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v42 + 144LL))(v42, v44);
                  if ( v8 < 0 )
                  {
                    v34 = v42;
                    if ( v42 )
                    {
                      v42 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                    }
                    v35 = v43;
                    if ( v43 )
                    {
                      v43 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                    }
                    goto LABEL_81;
                  }
                  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 144LL))(v43, &v51);
                  if ( v8 < 0 )
                  {
                    v32 = v42;
                    if ( v42 )
                    {
                      v42 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                    }
                    v33 = v43;
                    if ( v43 )
                    {
                      v43 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                    }
                    goto LABEL_81;
                  }
                  if ( (_WORD)v51 != v44[0] )
                  {
                    v29 = L"true";
                    if ( !v44[0] )
                      v29 = L"false";
                    LogLevelW(3u, L"Trigger enabled states did not match! Expected: %s; Actual: %s", v29);
                    v30 = v42;
                    if ( v42 )
                    {
                      v42 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                    }
                    v31 = v43;
                    if ( v43 )
                    {
                      v43 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    }
                    goto LABEL_31;
                  }
                  v47 = 0;
                  v48 = 0;
                  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 56LL))(v43, &v47);
                  if ( v8 < 0 )
                  {
                    v27 = v42;
                    if ( v42 )
                    {
                      v42 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                    }
                    v28 = v43;
                    if ( v43 )
                    {
                      v43 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                    }
                    goto LABEL_81;
                  }
                  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 56LL))(v42, &v48);
                  if ( v8 < 0 )
                  {
                    v25 = v42;
                    if ( v42 )
                    {
                      v42 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                    }
                    v26 = v43;
                    if ( v43 )
                    {
                      v43 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                    }
                    goto LABEL_81;
                  }
                  if ( v47 != v48 )
                  {
                    LogLevelW(3u, L"Trigger TASK_TRIGGER_TYPE2 did not match! Expected: %d; Actual: %d");
                    v23 = v42;
                    if ( v42 )
                    {
                      v42 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                    }
                    v24 = v43;
                    if ( v43 )
                    {
                      v43 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                    }
                    goto LABEL_31;
                  }
                  v16 = v42;
                  if ( v42 )
                  {
                    v42 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                  }
                  v17 = v43;
                  if ( v43 )
                  {
                    v43 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                  }
                  if ( (int)++v12 > v45 )
                    goto LABEL_30;
                }
                v38 = v42;
                if ( v42 )
                {
                  v42 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                }
                v39 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                }
                goto LABEL_81;
              }
LABEL_30:
              *a4 = 1;
            }
            else
            {
              LogLevelW(3u, L"Trigger counts did not match! Expected: %d; Actual: %d", v46, (unsigned int)v45);
            }
LABEL_31:
            v18 = v49;
            if ( v49 )
            {
              v49 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
            v19 = v50;
            if ( v50 )
            {
              v50 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            }
            v20 = *a1;
            if ( *a1 )
            {
              *a1 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            }
            v21 = *a2;
            if ( *a2 )
            {
              *a2 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            }
            return (unsigned int)v8;
          }
          LogLevelW(2u, L"Failed to get current task trigger count! hr = 0x%08x", (unsigned int)v11);
        }
        else
        {
          LogLevelW(2u, L"Failed to get expected task trigger count! hr = 0x%08x", (unsigned int)v10);
        }
      }
      else
      {
        LogLevelW(2u, L"Failed to get current task triggers! hr = 0x%08x", (unsigned int)v9);
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to get expected task triggers! hr = 0x%08x", (unsigned int)v7);
    }
LABEL_81:
    LogLevelW(
      2u,
      L"Error encountered when comparing current task triggers with expected task triggers. hr=0x%08x",
      (unsigned int)v8);
    goto LABEL_31;
  }
  LogLevelW(2u, L"Invalid pointer input for TasksHelper::CompareTriggers!");
  v40 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18005ec54  mov     [rsp-38h+arg_10], r8d
0x18005ec59  mov     [rsp-38h+arg_8], rdx
0x18005ec5e  mov     [rsp-38h+arg_0], rcx
0x18005ec63  push    rbp
0x18005ec64  push    rbx
0x18005ec65  push    rsi
0x18005ec66  push    r12
0x18005ec68  push    r13
0x18005ec6a  push    r14
0x18005ec6c  push    r15
0x18005ec6e  mov     rbp, rsp
0x18005ec71  sub     rsp, 60h
0x18005ec75  mov     r12, r9
0x18005ec78  mov     r14, rdx
0x18005ec7b  mov     r15, rcx
0x18005ec7e  xor     r13d, r13d
0x18005ec81  cmp     [rcx], r13
0x18005ec84  jz      loc_18005F168
0x18005ec8a  cmp     [rdx], r13
0x18005ec8d  jz      loc_18005F168
0x18005ec93  test    r9, r9
0x18005ec96  jz      loc_18005F168
0x18005ec9c  mov     [r9], r13b
0x18005ec9f  mov     [rbp+var_10], r13
0x18005eca3  mov     [rbp+var_18], r13
0x18005eca7  mov     rcx, [rcx]
0x18005ecaa  mov     rax, [rcx]
0x18005ecad  lea     rdx, [rbp+var_10]
0x18005ecb1  mov     rax, [rax+48h]
0x18005ecb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ecba  mov     ebx, eax
0x18005ecbc  test    eax, eax
0x18005ecbe  jns     short loc_18005ECD9
0x18005ecc0  lea     rdx, aFailedToGetExp; "Failed to get expected task triggers! h"...
0x18005ecc7  mov     r8d, eax
0x18005ecca  mov     ecx, 2; unsigned __int8
0x18005eccf  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005ecd4  jmp     loc_18005F14F
0x18005ecd9  mov     rcx, [r14]
0x18005ecdc  mov     rax, [rcx]
0x18005ecdf  lea     rdx, [rbp+var_18]
0x18005ece3  mov     rax, [rax+48h]
0x18005ece7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ecec  mov     ebx, eax
0x18005ecee  test    eax, eax
0x18005ecf0  jns     short loc_18005ECFB
0x18005ecf2  lea     rdx, aFailedToGetCur; "Failed to get current task triggers! hr"...
0x18005ecf9  jmp     short loc_18005ECC7
0x18005ecfb  mov     [rbp+var_28], r13d
0x18005ecff  mov     [rbp+var_2C], r13d
0x18005ed03  mov     rcx, [rbp+var_10]
0x18005ed07  mov     rax, [rcx]
0x18005ed0a  lea     rdx, [rbp+var_28]
0x18005ed0e  mov     rax, [rax+38h]
0x18005ed12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed17  mov     ebx, eax
0x18005ed19  test    eax, eax
0x18005ed1b  jns     short loc_18005ED26
0x18005ed1d  lea     rdx, aFailedToGetExp_0; "Failed to get expected task trigger cou"...
0x18005ed24  jmp     short loc_18005ECC7
0x18005ed26  mov     rcx, [rbp+var_18]
0x18005ed2a  mov     rax, [rcx]
0x18005ed2d  lea     rdx, [rbp+var_2C]
0x18005ed31  mov     rax, [rax+38h]
0x18005ed35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed3a  mov     ebx, eax
0x18005ed3c  test    eax, eax
0x18005ed3e  jns     short loc_18005ED4C
0x18005ed40  lea     rdx, aFailedToGetCur_0; "Failed to get current task trigger coun"...
0x18005ed47  jmp     loc_18005ECC7
0x18005ed4c  mov     r8d, [rbp+var_28]
0x18005ed50  mov     eax, [rbp+var_2C]
0x18005ed53  cmp     r8d, eax
0x18005ed56  jz      short loc_18005ED71
0x18005ed58  mov     r9d, eax
0x18005ed5b  lea     rdx, aTriggerCountsD; "Trigger counts did not match! Expected:"...
0x18005ed62  mov     ecx, 3; unsigned __int8
0x18005ed67  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005ed6c  jmp     loc_18005EEE4
0x18005ed71  mov     esi, 1
0x18005ed76  cmp     eax, esi
0x18005ed78  jl      loc_18005EEDF
0x18005ed7e  mov     [rbp+var_38], r13
0x18005ed82  mov     [rbp+var_40], r13
0x18005ed86  mov     rcx, [rbp+var_18]
0x18005ed8a  mov     rax, [rcx]
0x18005ed8d  lea     r8, [rbp+var_38]
0x18005ed91  mov     edx, esi
0x18005ed93  mov     rax, [rax+40h]
0x18005ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed9c  mov     ebx, eax
0x18005ed9e  test    eax, eax
0x18005eda0  js      loc_18005F11B
0x18005eda6  mov     rbx, [rbp+var_10]
0x18005edaa  mov     rax, [rbx]
0x18005edad  mov     r13, [rax+40h]
0x18005edb1  mov     rcx, [rbp+var_40]
0x18005edb5  test    rcx, rcx
0x18005edb8  jz      short loc_18005EDCF
0x18005edba  mov     [rbp+var_40], 0
0x18005edc2  mov     rdx, [rcx]
0x18005edc5  mov     rax, [rdx+10h]
0x18005edc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005edce  nop
0x18005edcf  lea     r8, [rbp+var_40]
0x18005edd3  mov     edx, esi
0x18005edd5  mov     rcx, rbx
0x18005edd8  mov     rax, r13
0x18005eddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ede0  mov     ebx, eax
0x18005ede2  xor     r13d, r13d
0x18005ede5  test    eax, eax
0x18005ede7  js      loc_18005F0E5
0x18005eded  or      eax, 0FFFFFFFFh
0x18005edf0  mov     word ptr [rbp+arg_10], ax
0x18005edf4  mov     [rbp+var_30], ax
0x18005edf8  mov     rcx, [rbp+var_40]
0x18005edfc  mov     rax, [rcx]
0x18005edff  lea     rdx, [rbp+var_30]
0x18005ee03  mov     rax, [rax+90h]
0x18005ee0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee0f  mov     ebx, eax
0x18005ee11  test    eax, eax
0x18005ee13  js      loc_18005F0AF
0x18005ee19  mov     rcx, [rbp+var_38]
0x18005ee1d  mov     rax, [rcx]
0x18005ee20  lea     rdx, [rbp+arg_10]
0x18005ee24  mov     rax, [rax+90h]
0x18005ee2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee30  mov     ebx, eax
0x18005ee32  test    eax, eax
0x18005ee34  js      loc_18005F076
0x18005ee3a  movzx   eax, word ptr [rbp+arg_10]
0x18005ee3e  movzx   ecx, [rbp+var_30]
0x18005ee42  cmp     ax, cx
0x18005ee45  jnz     loc_18005F00C
0x18005ee4b  mov     [rbp+var_24], r13d
0x18005ee4f  mov     [rbp+var_20], r13d
0x18005ee53  mov     rcx, [rbp+var_38]
0x18005ee57  mov     rax, [rcx]
0x18005ee5a  lea     rdx, [rbp+var_24]
0x18005ee5e  mov     rax, [rax+38h]
0x18005ee62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee67  mov     ebx, eax
0x18005ee69  test    eax, eax
0x18005ee6b  js      loc_18005EFD3
0x18005ee71  mov     rcx, [rbp+var_40]
0x18005ee75  mov     rax, [rcx]
0x18005ee78  lea     rdx, [rbp+var_20]
0x18005ee7c  mov     rax, [rax+38h]
0x18005ee80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ee85  mov     ebx, eax
0x18005ee87  test    eax, eax
0x18005ee89  js      loc_18005EF9A
0x18005ee8f  mov     r9d, [rbp+var_24]
0x18005ee93  mov     r8d, [rbp+var_20]
0x18005ee97  cmp     r9d, r8d
0x18005ee9a  jnz     loc_18005EF4F
0x18005eea0  mov     rcx, [rbp+var_40]
0x18005eea4  test    rcx, rcx
0x18005eea7  jz      short loc_18005EEBA
0x18005eea9  mov     [rbp+var_40], r13
0x18005eead  mov     rax, [rcx]
0x18005eeb0  mov     rax, [rax+10h]
0x18005eeb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eeb9  nop
0x18005eeba  mov     rcx, [rbp+var_38]
0x18005eebe  test    rcx, rcx
0x18005eec1  jz      short loc_18005EED4
0x18005eec3  mov     [rbp+var_38], r13
0x18005eec7  mov     rax, [rcx]
0x18005eeca  mov     rax, [rax+10h]
0x18005eece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eed3  nop
0x18005eed4  inc     esi
0x18005eed6  cmp     esi, [rbp+var_2C]
0x18005eed9  jle     loc_18005ED7E
0x18005eedf  mov     byte ptr [r12], 1
0x18005eee4  mov     rcx, [rbp+var_18]
0x18005eee8  test    rcx, rcx
0x18005eeeb  jz      short loc_18005EEFE
0x18005eeed  mov     [rbp+var_18], r13
0x18005eef1  mov     rax, [rcx]
0x18005eef4  mov     rax, [rax+10h]
0x18005eef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eefd  nop
0x18005eefe  mov     rcx, [rbp+var_10]
0x18005ef02  test    rcx, rcx
0x18005ef05  jz      short loc_18005EF18
0x18005ef07  mov     [rbp+var_10], r13
0x18005ef0b  mov     rax, [rcx]
0x18005ef0e  mov     rax, [rax+10h]
0x18005ef12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef17  nop
0x18005ef18  mov     rcx, [r15]
0x18005ef1b  test    rcx, rcx
0x18005ef1e  jz      short loc_18005EF30
0x18005ef20  mov     [r15], r13
0x18005ef23  mov     rax, [rcx]
0x18005ef26  mov     rax, [rax+10h]
0x18005ef2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef2f  nop
0x18005ef30  mov     rcx, [r14]
0x18005ef33  test    rcx, rcx
0x18005ef36  jz      short loc_18005EF48
0x18005ef38  mov     [r14], r13
0x18005ef3b  mov     rax, [rcx]
0x18005ef3e  mov     rax, [rax+10h]
0x18005ef42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef47  nop
0x18005ef48  mov     eax, ebx
0x18005ef4a  jmp     loc_18005F1AF
0x18005ef4f  lea     rdx, aTriggerTaskTri; "Trigger TASK_TRIGGER_TYPE2 did not matc"...
0x18005ef56  mov     ecx, 3; unsigned __int8
0x18005ef5b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005ef60  nop
0x18005ef61  mov     rcx, [rbp+var_40]
0x18005ef65  test    rcx, rcx
0x18005ef68  jz      short loc_18005EF7B
0x18005ef6a  mov     [rbp+var_40], r13
0x18005ef6e  mov     rax, [rcx]
0x18005ef71  mov     rax, [rax+10h]
0x18005ef75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef7a  nop
0x18005ef7b  mov     rcx, [rbp+var_38]
0x18005ef7f  test    rcx, rcx
0x18005ef82  jz      short loc_18005EF95
0x18005ef84  mov     [rbp+var_38], r13
0x18005ef88  mov     rax, [rcx]
0x18005ef8b  mov     rax, [rax+10h]
0x18005ef8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef94  nop
0x18005ef95  jmp     loc_18005EEE4
0x18005ef9a  mov     rcx, [rbp+var_40]
0x18005ef9e  test    rcx, rcx
0x18005efa1  jz      short loc_18005EFB4
0x18005efa3  mov     [rbp+var_40], r13
0x18005efa7  mov     rax, [rcx]
0x18005efaa  mov     rax, [rax+10h]
0x18005efae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efb3  nop
0x18005efb4  mov     rcx, [rbp+var_38]
0x18005efb8  test    rcx, rcx
0x18005efbb  jz      short loc_18005EFCE
0x18005efbd  mov     [rbp+var_38], r13
0x18005efc1  mov     rax, [rcx]
0x18005efc4  mov     rax, [rax+10h]
0x18005efc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efcd  nop
0x18005efce  jmp     loc_18005F14F
0x18005efd3  mov     rcx, [rbp+var_40]
0x18005efd7  test    rcx, rcx
0x18005efda  jz      short loc_18005EFED
0x18005efdc  mov     [rbp+var_40], r13
0x18005efe0  mov     rax, [rcx]
0x18005efe3  mov     rax, [rax+10h]
0x18005efe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efec  nop
0x18005efed  mov     rcx, [rbp+var_38]
0x18005eff1  test    rcx, rcx
0x18005eff4  jz      short loc_18005F007
0x18005eff6  mov     [rbp+var_38], r13
0x18005effa  mov     rax, [rcx]
0x18005effd  mov     rax, [rax+10h]
0x18005f001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f006  nop
0x18005f007  jmp     loc_18005F14F
0x18005f00c  lea     r9, aTrue; "true"
0x18005f013  mov     r8, r9
0x18005f016  lea     rdx, aFalse_0; "false"
0x18005f01d  test    cx, cx
0x18005f020  cmovz   r8, rdx
0x18005f024  test    ax, ax
0x18005f027  cmovz   r9, rdx
0x18005f02b  lea     rdx, aTriggerEnabled; "Trigger enabled states did not match! E"...
0x18005f032  mov     ecx, 3; unsigned __int8
0x18005f037  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f03c  nop
0x18005f03d  mov     rcx, [rbp+var_40]
0x18005f041  test    rcx, rcx
0x18005f044  jz      short loc_18005F057
0x18005f046  mov     [rbp+var_40], r13
0x18005f04a  mov     rax, [rcx]
0x18005f04d  mov     rax, [rax+10h]
0x18005f051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f056  nop
0x18005f057  mov     rcx, [rbp+var_38]
0x18005f05b  test    rcx, rcx
0x18005f05e  jz      short loc_18005F071
0x18005f060  mov     [rbp+var_38], r13
0x18005f064  mov     rax, [rcx]
0x18005f067  mov     rax, [rax+10h]
0x18005f06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f070  nop
0x18005f071  jmp     loc_18005EEE4
0x18005f076  mov     rcx, [rbp+var_40]
0x18005f07a  test    rcx, rcx
0x18005f07d  jz      short loc_18005F090
0x18005f07f  mov     [rbp+var_40], r13
0x18005f083  mov     rax, [rcx]
  ... truncated ...
```
