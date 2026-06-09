# HandleCreateSpaceRequest(TASK_CREATE_SPACE_REQUEST const *,_GUID *)

- ea: `0x140018a8c`
- end: `0x140018cf6`
- name: `?HandleCreateSpaceRequest@@YAHPEBUTASK_CREATE_SPACE_REQUEST@@PEAU_GUID@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(const struct TASK_CREATE_SPACE_REQUEST *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x140017d70`

## callees

- `0x14000a440`
- `0x140012fb0`
- `0x140016bc4`
- `0x140016eac`
- `0x14001832c`
- `0x140018a8c`
- `0x140018cfc`
- `0x14001a714`
- `0x14001ed86`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140018bfa`
- `KERNEL32!LocalFree` at `0x140018c1e`
- `KERNEL32!LocalFree` at `0x140018c42`
- `KERNEL32!LocalFree` at `0x140018c66`
- `KERNEL32!LocalFree` at `0x140018bfa`
- `KERNEL32!LocalFree` at `0x140018c1e`
- `KERNEL32!LocalFree` at `0x140018c42`
- `KERNEL32!LocalFree` at `0x140018c66`
- `KERNEL32!SetLastError` at `0x140018af6`
- `KERNEL32!SetLastError` at `0x140018cd6`
- `KERNEL32!SetLastError` at `0x140018af6`
- `KERNEL32!SetLastError` at `0x140018cd6`
- `KERNEL32!GetLastError` at `0x140018bea`
- `KERNEL32!GetLastError` at `0x140018c0e`
- `KERNEL32!GetLastError` at `0x140018c32`
- `KERNEL32!GetLastError` at `0x140018c56`
- `KERNEL32!GetLastError` at `0x140018c7a`
- `KERNEL32!GetLastError` at `0x140018bea`
- `KERNEL32!GetLastError` at `0x140018c0e`
- `KERNEL32!GetLastError` at `0x140018c32`
- `KERNEL32!GetLastError` at `0x140018c56`
- `KERNEL32!GetLastError` at `0x140018c7a`

## pseudocode

```c
__int64 __fastcall HandleCreateSpaceRequest(const struct TASK_CREATE_SPACE_REQUEST *a1, struct _GUID *a2)
{
  struct _SU_POOL_OBJECT *v3; // r12
  unsigned __int16 *v4; // r13
  unsigned __int16 *v5; // r15
  unsigned int SpaceTemplate; // ebx
  DWORD v8; // ecx
  unsigned int Pool; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  DWORD LastError; // edi
  HLOCAL v14; // rax
  HLOCAL v15; // rax
  HLOCAL v16; // rax
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  struct _SU_POOL_OBJECT *v20; // [rsp+38h] [rbp-38h] BYREF
  _OWORD v21[3]; // [rsp+40h] [rbp-30h] BYREF
  struct _SU_SPACE_OBJECT *v23; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int16 *v24; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  v20 = 0;
  v4 = 0;
  v5 = 0;
  v23 = 0;
  v24 = 0;
  *a2 = GUID_NULL;
  SpaceTemplate = IssueProgressStringResult(32890);
  if ( SpaceTemplate )
  {
    if ( *(_QWORD *)a1 != 576 )
    {
      v8 = 24;
LABEL_4:
      SpaceTemplate = 0;
      SetLastError(v8);
      goto LABEL_14;
    }
    Pool = SiGetPool((struct _GUID *)a1 + 1, 0, &v20);
    v3 = v20;
    SpaceTemplate = Pool;
    if ( Pool )
    {
      SpaceTemplate = SuGetSpaceTemplate(v20, v10, *((unsigned int *)a1 + 139));
      if ( SpaceTemplate )
      {
        SpaceTemplate = SuInitializeSpaceTemplateEx(0, (const unsigned __int16 *)a1 + 21, *((_DWORD *)a1 + 140));
        if ( SpaceTemplate )
        {
          MEMORY[0xA68] = *((_QWORD *)a1 + 71);
          if ( MEMORY[0xA68] > 0x3F0000000000uLL )
          {
            v8 = 87;
            goto LABEL_4;
          }
          v11 = SuCreateSpaceEx(v3, 0, &v23, &v24);
          v4 = (unsigned __int16 *)v23;
          SpaceTemplate = v11;
          if ( v11 )
          {
            *a2 = *(struct _GUID *)((char *)v23 + 56);
            v12 = IssueProgressStringResult(32891);
            v5 = v24;
            SpaceTemplate = v12;
            if ( v12 )
            {
              LOWORD(v23) = *((_WORD *)a1 + 277);
              SpaceTemplate = FormatDisk(v24, (const unsigned __int16 *)a1 + 16, v4 + 56, (unsigned __int16 *)&v23);
            }
          }
          else
          {
            v5 = v24;
          }
        }
      }
    }
  }
LABEL_14:
  LastError = GetLastError();
  if ( v5 )
  {
    v14 = LocalFree(v5);
    if ( SpaceTemplate )
    {
      SpaceTemplate = v14 == 0;
      LastError = GetLastError();
    }
  }
  if ( v4 )
  {
    v15 = LocalFree(v4);
    if ( SpaceTemplate )
    {
      SpaceTemplate = v15 == 0;
      LastError = GetLastError();
    }
  }
  if ( v3 )
  {
    v16 = LocalFree(v3);
    if ( SpaceTemplate )
    {
      SpaceTemplate = v16 == 0;
      LastError = GetLastError();
    }
  }
  if ( !SpaceTemplate && memcmp_0(a2, &GUID_NULL, 0x10u) )
  {
    v17 = (__int128)*a2;
    v21[0] = 0x30u;
    v18 = *((_OWORD *)a1 + 1);
    DWORD2(v21[0]) = 9;
    v21[2] = v17;
    v21[1] = v18;
    HandleDestroySpaceRequest((const struct TASK_DESTROY_SPACE_REQUEST *)v21);
  }
  SetLastError(LastError);
  return SpaceTemplate;
}

```

## disassembly

```asm
0x140018a8c  mov     [rsp-38h+arg_0], rbx
0x140018a91  mov     [rsp-38h+Buf1], rdx
0x140018a96  push    rbp
0x140018a97  push    rsi
0x140018a98  push    rdi
0x140018a99  push    r12
0x140018a9b  push    r13
0x140018a9d  push    r14
0x140018a9f  push    r15
0x140018aa1  mov     rbp, rsp
0x140018aa4  sub     rsp, 70h
0x140018aa8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140018aaf  mov     r14, rcx
0x140018ab2  xor     r12d, r12d
0x140018ab5  xor     esi, esi
0x140018ab7  mov     [rbp+var_38], r12
0x140018abb  xor     r13d, r13d
0x140018abe  mov     [rbp+var_40], rsi
0x140018ac2  xor     r15d, r15d
0x140018ac5  mov     [rbp+arg_10], r13
0x140018ac9  mov     ecx, 807Ah
0x140018ace  mov     [rbp+arg_18], r15
0x140018ad2  movdqu  xmmword ptr [rdx], xmm0
0x140018ad6  mov     rdi, rdx
0x140018ad9  call    IssueProgressStringResult
0x140018ade  mov     ebx, eax
0x140018ae0  test    eax, eax
0x140018ae2  jz      loc_140018BEA
0x140018ae8  cmp     qword ptr [r14], 240h
0x140018aef  jz      short loc_140018B01
0x140018af1  lea     ecx, [rsi+18h]; dwErrCode
0x140018af4  xor     ebx, ebx
0x140018af6  call    cs:__imp_SetLastError
0x140018afc  jmp     loc_140018BEA
0x140018b01  lea     rcx, [r14+10h]; struct _GUID *
0x140018b05  xor     edx, edx; unsigned int
0x140018b07  lea     r8, [rbp+var_38]; struct _SU_POOL_OBJECT **
0x140018b0b  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x140018b10  mov     r12, [rbp+var_38]
0x140018b14  mov     ebx, eax
0x140018b16  test    eax, eax
0x140018b18  jz      loc_140018BEA
0x140018b1e  mov     r8d, [r14+22Ch]
0x140018b25  lea     rax, [rbp+var_40]
0x140018b29  mov     rcx, r12
0x140018b2c  mov     [rsp+70h+var_50], rax
0x140018b31  call    ?SuGetSpaceTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SC_SPACE_USAGE@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_SPACE_INFO@@@Z; SuGetSpaceTemplate(_SU_POOL_OBJECT *,_SC_SPACE_USAGE,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_SPACE_INFO * *)
0x140018b36  mov     rsi, [rbp+var_40]
0x140018b3a  mov     ebx, eax
0x140018b3c  test    eax, eax
0x140018b3e  jz      loc_140018BEA
0x140018b44  mov     r8d, [r14+230h]; unsigned int
0x140018b4b  lea     rdx, [r14+2Ah]; unsigned __int16 *
0x140018b4f  mov     rcx, rsi; struct _SP_SPACE_INFO *
0x140018b52  call    ?SuInitializeSpaceTemplateEx@@YAHPEAU_SP_SPACE_INFO@@PEBGI@Z; SuInitializeSpaceTemplateEx(_SP_SPACE_INFO *,ushort const *,uint)
0x140018b57  mov     ebx, eax
0x140018b59  test    eax, eax
0x140018b5b  jz      loc_140018BEA
0x140018b61  mov     rax, [r14+238h]
0x140018b68  mov     rcx, 3F0000000000h
0x140018b72  mov     [rsi+0A68h], rax
0x140018b79  cmp     rax, rcx
0x140018b7c  jbe     short loc_140018B88
0x140018b7e  mov     ecx, 57h ; 'W'
0x140018b83  jmp     loc_140018AF4
0x140018b88  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x140018b8c  mov     rdx, rsi; struct _SP_SPACE_INFO *
0x140018b8f  lea     r8, [rbp+arg_10]; struct _SU_SPACE_OBJECT **
0x140018b93  mov     rcx, r12; struct _SU_POOL_OBJECT *
0x140018b96  call    ?SuCreateSpaceEx@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@PEAPEAU_SU_SPACE_OBJECT@@PEAPEAG@Z; SuCreateSpaceEx(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SU_SPACE_OBJECT * *,ushort * *)
0x140018b9b  mov     r13, [rbp+arg_10]
0x140018b9f  mov     ebx, eax
0x140018ba1  test    eax, eax
0x140018ba3  jz      short loc_140018BE6
0x140018ba5  movups  xmm0, xmmword ptr [r13+38h]
0x140018baa  mov     ecx, 807Bh
0x140018baf  movdqu  xmmword ptr [rdi], xmm0
0x140018bb3  call    IssueProgressStringResult
0x140018bb8  mov     r15, [rbp+arg_18]
0x140018bbc  mov     ebx, eax
0x140018bbe  test    eax, eax
0x140018bc0  jz      short loc_140018BEA
0x140018bc2  movzx   eax, word ptr [r14+22Ah]
0x140018bca  lea     r8, [r13+70h]; unsigned __int16 *
0x140018bce  lea     rdx, [r14+20h]; unsigned __int16 *
0x140018bd2  mov     word ptr [rbp+arg_10], ax
0x140018bd6  lea     r9, [rbp+arg_10]; unsigned __int16 *
0x140018bda  mov     rcx, r15; unsigned __int16 *
0x140018bdd  call    ?FormatDisk@@YAHPEBG00PEAG@Z; FormatDisk(ushort const *,ushort const *,ushort const *,ushort *)
0x140018be2  mov     ebx, eax
0x140018be4  jmp     short loc_140018BEA
0x140018be6  mov     r15, [rbp+arg_18]
0x140018bea  call    cs:__imp_GetLastError
0x140018bf0  mov     edi, eax
0x140018bf2  test    r15, r15
0x140018bf5  jz      short loc_140018C16
0x140018bf7  mov     rcx, r15; hMem
0x140018bfa  call    cs:__imp_LocalFree
0x140018c00  xor     ecx, ecx
0x140018c02  test    rax, rax
0x140018c05  setz    cl
0x140018c08  test    ebx, ebx
0x140018c0a  jz      short loc_140018C16
0x140018c0c  mov     ebx, ecx
0x140018c0e  call    cs:__imp_GetLastError
0x140018c14  mov     edi, eax
0x140018c16  test    r13, r13
0x140018c19  jz      short loc_140018C3A
0x140018c1b  mov     rcx, r13; hMem
0x140018c1e  call    cs:__imp_LocalFree
0x140018c24  xor     ecx, ecx
0x140018c26  test    rax, rax
0x140018c29  setz    cl
0x140018c2c  test    ebx, ebx
0x140018c2e  jz      short loc_140018C3A
0x140018c30  mov     ebx, ecx
0x140018c32  call    cs:__imp_GetLastError
0x140018c38  mov     edi, eax
0x140018c3a  test    r12, r12
0x140018c3d  jz      short loc_140018C5E
0x140018c3f  mov     rcx, r12; hMem
0x140018c42  call    cs:__imp_LocalFree
0x140018c48  xor     ecx, ecx
0x140018c4a  test    rax, rax
0x140018c4d  setz    cl
0x140018c50  test    ebx, ebx
0x140018c52  jz      short loc_140018C5E
0x140018c54  mov     ebx, ecx
0x140018c56  call    cs:__imp_GetLastError
0x140018c5c  mov     edi, eax
0x140018c5e  test    rsi, rsi
0x140018c61  jz      short loc_140018C82
0x140018c63  mov     rcx, rsi; hMem
0x140018c66  call    cs:__imp_LocalFree
0x140018c6c  xor     ecx, ecx
0x140018c6e  test    rax, rax
0x140018c71  setz    cl
0x140018c74  test    ebx, ebx
0x140018c76  jz      short loc_140018C86
0x140018c78  mov     ebx, ecx
0x140018c7a  call    cs:__imp_GetLastError
0x140018c80  mov     edi, eax
0x140018c82  test    ebx, ebx
0x140018c84  jnz     short loc_140018CD4
0x140018c86  mov     rsi, [rbp+Buf1]
0x140018c8a  lea     rdx, GUID_NULL; Buf2
0x140018c91  mov     rcx, rsi; Buf1
0x140018c94  mov     r8d, 10h; Size
0x140018c9a  call    memcmp_0
0x140018c9f  test    eax, eax
0x140018ca1  jz      short loc_140018CD4
0x140018ca3  movups  xmm1, xmmword ptr [rsi]
0x140018ca6  lea     rcx, [rbp+var_30]; struct TASK_DESTROY_SPACE_REQUEST *
0x140018caa  xorps   xmm0, xmm0
0x140018cad  movups  [rbp+var_30], xmm0
0x140018cb1  mov     qword ptr [rbp+var_30], 30h ; '0'
0x140018cb9  movups  xmm0, xmmword ptr [r14+10h]
0x140018cbe  mov     dword ptr [rbp+var_30+8], 9
0x140018cc5  movdqu  [rbp+var_10], xmm1
0x140018cca  movdqu  [rbp+var_20], xmm0
0x140018ccf  call    ?HandleDestroySpaceRequest@@YAHPEBUTASK_DESTROY_SPACE_REQUEST@@@Z; HandleDestroySpaceRequest(TASK_DESTROY_SPACE_REQUEST const *)
0x140018cd4  mov     ecx, edi; dwErrCode
0x140018cd6  call    cs:__imp_SetLastError
0x140018cdc  mov     eax, ebx
0x140018cde  mov     rbx, [rsp+70h+arg_0]
0x140018ce6  add     rsp, 70h
0x140018cea  pop     r15
0x140018cec  pop     r14
0x140018cee  pop     r13
0x140018cf0  pop     r12
0x140018cf2  pop     rdi
0x140018cf3  pop     rsi
0x140018cf4  pop     rbp
0x140018cf5  retn
```
