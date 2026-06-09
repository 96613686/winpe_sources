# SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)

- ea: `0x14001343c`
- end: `0x14001350d`
- name: `?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fed8`
- `0x140010104`
- `0x140010694`
- `0x1400107e8`
- `0x140010a68`
- `0x140011248`
- `0x1400114f8`

## callees

- `0x140011f24`
- `0x140011f54`
- `0x14001343c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400134b8`
- `KERNEL32!LocalFree` at `0x1400134b8`
- `KERNEL32!SetLastError` at `0x140013464`
- `KERNEL32!SetLastError` at `0x1400134ad`
- `KERNEL32!SetLastError` at `0x140013464`
- `KERNEL32!SetLastError` at `0x1400134ad`
- `KERNEL32!LocalAlloc` at `0x14001347a`
- `KERNEL32!LocalAlloc` at `0x14001347a`
- `RPCRT4!UuidCreate` at `0x1400134a1`
- `RPCRT4!UuidCreate` at `0x1400134a1`

## pseudocode

```c
__int64 __fastcall SuGetTierTemplate(__int64 a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  bool v4; // cc
  DWORD v8; // ecx
  unsigned int v9; // edi
  char *v10; // rax
  _DWORD *v11; // rbx
  RPC_STATUS v12; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx

  v4 = *(_DWORD *)(a1 + 2644) <= 3u;
  *a4 = 0;
  if ( v4 )
  {
    v8 = 50;
LABEL_3:
    SetLastError(v8);
    return 0;
  }
  v10 = (char *)LocalAlloc(0x40u, 0xB40u);
  v11 = v10;
  if ( !v10 )
  {
    v8 = 1450;
    goto LABEL_3;
  }
  *(_DWORD *)v10 = 2880;
  *((_DWORD *)v10 + 1) = 2880;
  *(_OWORD *)(v10 + 8) = *(_OWORD *)(a1 + 40);
  v12 = UuidCreate((UUID *)(v10 + 24));
  if ( v12 )
  {
    SetLastError(v12);
    v9 = 0;
  }
  else
  {
    v11[654] = 1;
    if ( !a2 )
      a2 = *(_DWORD *)(a1 + 2776);
    v9 = SiInitializeProvisioning(a1, a2, v11 + 662);
    if ( v9 )
    {
      v9 = SiInitializeResiliency(v15, v14, v11 + 673);
      if ( v9 )
      {
        *a4 = v11;
        return v9;
      }
    }
  }
  LocalFree(v11);
  return v9;
}

```

## disassembly

```asm
0x14001343c  push    rbx
0x14001343e  push    rbp
0x14001343f  push    rsi
0x140013440  push    rdi
0x140013441  push    r14
0x140013443  sub     rsp, 20h
0x140013447  cmp     dword ptr [rcx+0A54h], 3
0x14001344e  mov     r14, r9
0x140013451  mov     ebp, edx
0x140013453  mov     qword ptr [r9], 0
0x14001345a  mov     rsi, rcx
0x14001345d  ja      short loc_14001346E
0x14001345f  mov     ecx, 32h ; '2'; dwErrCode
0x140013464  call    cs:__imp_SetLastError
0x14001346a  xor     edi, edi
0x14001346c  jmp     short loc_1400134BE
0x14001346e  mov     edi, 0B40h
0x140013473  mov     ecx, 40h ; '@'; uFlags
0x140013478  mov     edx, edi; uBytes
0x14001347a  call    cs:__imp_LocalAlloc
0x140013480  mov     rbx, rax
0x140013483  test    rax, rax
0x140013486  jnz     short loc_14001348F
0x140013488  mov     ecx, 5AAh
0x14001348d  jmp     short loc_140013464
0x14001348f  mov     [rax], edi
0x140013491  lea     rcx, [rax+18h]; Uuid
0x140013495  mov     [rax+4], edi
0x140013498  movups  xmm0, xmmword ptr [rsi+28h]
0x14001349c  movdqu  xmmword ptr [rax+8], xmm0
0x1400134a1  call    cs:__imp_UuidCreate
0x1400134a7  test    eax, eax
0x1400134a9  jz      short loc_1400134CB
0x1400134ab  mov     ecx, eax; dwErrCode
0x1400134ad  call    cs:__imp_SetLastError
0x1400134b3  xor     edi, edi
0x1400134b5  mov     rcx, rbx; hMem
0x1400134b8  call    cs:__imp_LocalFree
0x1400134be  mov     eax, edi
0x1400134c0  add     rsp, 20h
0x1400134c4  pop     r14
0x1400134c6  pop     rdi
0x1400134c7  pop     rsi
0x1400134c8  pop     rbp
0x1400134c9  pop     rbx
0x1400134ca  retn
0x1400134cb  mov     dword ptr [rbx+0A38h], 1
0x1400134d5  test    ebp, ebp
0x1400134d7  jnz     short loc_1400134DF
0x1400134d9  mov     ebp, [rsi+0AD8h]
0x1400134df  lea     r8, [rbx+0A58h]
0x1400134e6  mov     edx, ebp
0x1400134e8  mov     rcx, rsi
0x1400134eb  call    ?SiInitializeProvisioning@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_PROVISIONING_INFO@@@Z; SiInitializeProvisioning(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_PROVISIONING_INFO *)
0x1400134f0  mov     edi, eax
0x1400134f2  test    eax, eax
0x1400134f4  jz      short loc_1400134B5
0x1400134f6  lea     r8, [rbx+0A84h]
0x1400134fd  call    ?SiInitializeResiliency@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAVSP_RESILIENCY_INFO@@@Z; SiInitializeResiliency(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,SP_RESILIENCY_INFO *)
0x140013502  mov     edi, eax
0x140013504  test    eax, eax
0x140013506  jz      short loc_1400134B5
0x140013508  mov     [r14], rbx
0x14001350b  jmp     short loc_1400134BE
```
