# SuCreateSpace(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const,_SU_SPACE_OBJECT * *)

- ea: `0x140012704`
- end: `0x140012974`
- name: `?SuCreateSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@PEAPEAU_SU_SPACE_OBJECT@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, __int64, struct _SP_TIER_INFO **const, struct _SU_SPACE_OBJECT **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140016bc4`

## callees

- `0x140004114`
- `0x14000e860`
- `0x14000fea0`
- `0x1400105bc`
- `0x140010b5c`
- `0x140011684`
- `0x1400119c4`
- `0x140011bb8`
- `0x140011edc`
- `0x140012704`
- `0x140012d38`
- `0x140013a08`
- `0x140013b54`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400127d2`
- `KERNEL32!SetLastError` at `0x1400127d2`
- `KERNEL32!GetLastError` at `0x140012918`
- `KERNEL32!GetLastError` at `0x140012918`
- `KERNEL32!QueryPerformanceCounter` at `0x140012744`
- `KERNEL32!QueryPerformanceCounter` at `0x1400128b1`
- `KERNEL32!QueryPerformanceCounter` at `0x140012744`
- `KERNEL32!QueryPerformanceCounter` at `0x1400128b1`

## string_xrefs

- `0x1400127da`: `Invalid TierCount and Template ProvisionedCapacity specification`
- `0x140012831`: `SiCreateSpace`
- `0x140012851`: `SiCreateChildren`

## pseudocode

```c
__int64 __fastcall SuCreateSpace(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        __int64 a3,
        struct _SP_TIER_INFO **const a4,
        struct _SU_SPACE_OBJECT **a5)
{
  int v7; // r15d
  struct _SP_IDS *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int Space; // ebx
  __int64 v12; // xmm0_8
  __int64 v13; // r8
  struct _SP_TIER_INFO **v14; // r9
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-21h] BYREF
  LARGE_INTEGER v17; // [rsp+68h] [rbp-19h] BYREF
  _DWORD v18[22]; // [rsp+78h] [rbp-9h] BYREF

  memset(&v18[1], 0, 28);
  v7 = 0;
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  *a5 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v9 = *(_QWORD *)&GUID_NULL.Data1;
  if ( *((_QWORD *)a2 + 353) != *(_QWORD *)&GUID_NULL.Data1
    || (v10 = *(_QWORD *)GUID_NULL.Data4, *((_QWORD *)a2 + 354) != *(_QWORD *)GUID_NULL.Data4) )
  {
    Space = SiFixupSnapshot(a1, a2);
    if ( !Space )
      goto LABEL_16;
    v10 = *(_QWORD *)GUID_NULL.Data4;
    v9 = *(_QWORD *)&GUID_NULL.Data1;
  }
  if ( *((_QWORD *)a2 + 355) == v9 && *((_QWORD *)a2 + 356) == v10 || (Space = SiFixupReserve(a1, a2)) != 0 )
  {
    if ( *((_QWORD *)a2 + 333) )
    {
      v12 = *(_QWORD *)((char *)a1 + 44);
      v18[0] = *((_DWORD *)a1 + 10);
      v18[3] = *((_DWORD *)a1 + 13);
      *(_QWORD *)&v18[1] = v12;
      Space = SuRebalanceMetadata((struct _SP_ID *)v18, v8);
      if ( Space )
      {
        Space = SiCreateSpace(a1, a2, 0, 0);
        if ( Space )
        {
          v7 = 1;
          Space = SiCreateChildren(a1, a2, v13, v14);
          if ( Space )
          {
            Space = SiGrowSpace((struct _SP_SPACE_INFO *)((char *)a2 + 8));
            if ( Space )
            {
              Space = SiFinalizeSpace((struct _SP_SPACE_INFO *)((char *)a2 + 8));
              if ( Space )
              {
                v7 = 0;
                Space = SuGetSpace(a1, (struct _GUID *)((char *)a2 + 24), a5);
              }
            }
          }
        }
      }
    }
    else
    {
      SetLastError(0x57u);
      Space = 0;
    }
  }
LABEL_16:
  QueryPerformanceCounter(&v17);
  if ( Space )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjjzqx_EventWriteTransfer(
        *((unsigned __int8 *)a2 + 2600),
        (_DWORD)a2 + 40,
        (_DWORD)a2 + 24,
        (_DWORD)a1 + 40);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    GetLastError();
    McTemplateK0zsjjzqsq_EventWriteTransfer(
      *((unsigned __int8 *)a2 + 2600),
      (_DWORD)a2 + 40,
      (_DWORD)a2 + 24,
      (_DWORD)a1 + 40);
  }
  if ( v7 )
    SiCleanupSpace((struct _SP_SPACE_INFO *)((char *)a2 + 8));
  return Space;
}

```

## disassembly

```asm
0x140012704  push    rbp
0x140012706  push    rbx
0x140012707  push    rsi
0x140012708  push    rdi
0x140012709  push    r12
0x14001270b  push    r14
0x14001270d  push    r15
0x14001270f  lea     rbp, [rsp-1Fh]
0x140012714  sub     rsp, 0A0h
0x14001271b  xorps   xmm0, xmm0
0x14001271e  mov     r14, rcx
0x140012721  movups  xmmword ptr [rbp+4Fh+var_54], xmm0
0x140012725  lea     rcx, [rbp+4Fh+PerformanceCount]; this
0x140012729  mov     rdi, rdx
0x14001272c  movups  xmmword ptr [rbp+4Fh+var_54+0Ch], xmm0
0x140012730  xor     r15d, r15d
0x140012733  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x140012738  mov     r12, [rbp+4Fh+arg_20]
0x14001273c  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x140012740  mov     [r12], r15
0x140012744  call    cs:__imp_QueryPerformanceCounter
0x14001274a  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x140012751  cmp     [rdi+0B08h], rcx
0x140012758  jnz     short loc_14001276A
0x14001275a  mov     rax, qword ptr cs:GUID_NULL.Data4
0x140012761  cmp     [rdi+0B10h], rax
0x140012768  jz      short loc_140012795
0x14001276a  mov     rdx, rdi; struct _SP_SPACE_INFO *
0x14001276d  mov     rcx, r14; struct _SU_POOL_OBJECT *
0x140012770  call    ?SiFixupSnapshot@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@@Z; SiFixupSnapshot(_SU_POOL_OBJECT *,_SP_SPACE_INFO *)
0x140012775  mov     ebx, eax
0x140012777  test    eax, eax
0x140012779  jnz     short loc_140012787
0x14001277b  lea     rsi, aSifixupsnapsho; "SiFixupSnapshot"
0x140012782  jmp     loc_1400128AD
0x140012787  mov     rax, qword ptr cs:GUID_NULL.Data4
0x14001278e  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x140012795  cmp     [rdi+0B18h], rcx
0x14001279c  jnz     short loc_1400127A7
0x14001279e  cmp     [rdi+0B20h], rax
0x1400127a5  jz      short loc_1400127C4
0x1400127a7  mov     rdx, rdi; struct _SP_SPACE_INFO *
0x1400127aa  mov     rcx, r14; struct _SU_POOL_OBJECT *
0x1400127ad  call    ?SiFixupReserve@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@@Z; SiFixupReserve(_SU_POOL_OBJECT *,_SP_SPACE_INFO *)
0x1400127b2  mov     ebx, eax
0x1400127b4  test    eax, eax
0x1400127b6  jnz     short loc_1400127C4
0x1400127b8  lea     rsi, aSifixupreserve; "SiFixupReserve"
0x1400127bf  jmp     loc_1400128AD
0x1400127c4  cmp     [rdi+0A68h], r15
0x1400127cb  jnz     short loc_1400127E6
0x1400127cd  mov     ecx, 57h ; 'W'; dwErrCode
0x1400127d2  call    cs:__imp_SetLastError
0x1400127d8  xor     ebx, ebx
0x1400127da  lea     rsi, aInvalidTiercou; "Invalid TierCount and Template Provisio"...
0x1400127e1  jmp     loc_1400128AD
0x1400127e6  mov     eax, [r14+28h]
0x1400127ea  lea     rcx, [rbp+4Fh+var_58]; struct _SP_ID *
0x1400127ee  movsd   xmm0, qword ptr [r14+2Ch]
0x1400127f4  mov     [rbp+4Fh+var_58], eax
0x1400127f7  mov     eax, [r14+34h]
0x1400127fb  mov     dword ptr [rbp+4Fh+var_54+8], eax
0x1400127fe  movsd   qword ptr [rbp+4Fh+var_54], xmm0
0x140012803  call    ?SuRebalanceMetadata@@YAHPEAU_SP_ID@@PEAU_SP_IDS@@@Z; SuRebalanceMetadata(_SP_ID *,_SP_IDS *)
0x140012808  mov     ebx, eax
0x14001280a  test    eax, eax
0x14001280c  jnz     short loc_14001281A
0x14001280e  lea     rsi, aSurebalancemet; "SuRebalanceMetadata"
0x140012815  jmp     loc_1400128AD
0x14001281a  xor     r9d, r9d; struct _SP_TIER_INFO **
0x14001281d  xor     r8d, r8d; unsigned int
0x140012820  mov     rdx, rdi; struct _SP_SPACE_INFO *
0x140012823  mov     rcx, r14; struct _SU_POOL_OBJECT *
0x140012826  call    ?SiCreateSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@@Z; SiCreateSpace(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const)
0x14001282b  mov     ebx, eax
0x14001282d  test    eax, eax
0x14001282f  jnz     short loc_14001283A
0x140012831  lea     rsi, aSicreatespace; "SiCreateSpace"
0x140012838  jmp     short loc_1400128AD
0x14001283a  mov     rdx, rdi; struct _SP_SPACE_INFO *
0x14001283d  mov     rcx, r14; struct _SU_POOL_OBJECT *
0x140012840  mov     r15d, 1
0x140012846  call    ?SiCreateChildren@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@@Z; SiCreateChildren(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const)
0x14001284b  mov     ebx, eax
0x14001284d  test    eax, eax
0x14001284f  jnz     short loc_14001285A
0x140012851  lea     rsi, aSicreatechildr; "SiCreateChildren"
0x140012858  jmp     short loc_1400128AD
0x14001285a  lea     rcx, [rdi+8]; lpInBuffer
0x14001285e  call    ?SiGrowSpace@@YAHPEAU_SP_ID@@@Z; SiGrowSpace(_SP_ID *)
0x140012863  mov     ebx, eax
0x140012865  test    eax, eax
0x140012867  jnz     short loc_140012872
0x140012869  lea     rsi, aSigrowspace; "SiGrowSpace"
0x140012870  jmp     short loc_1400128AD
0x140012872  lea     rcx, [rdi+8]; lpInBuffer
0x140012876  call    ?SiFinalizeSpace@@YAHPEAU_SP_ID@@@Z; SiFinalizeSpace(_SP_ID *)
0x14001287b  mov     ebx, eax
0x14001287d  test    eax, eax
0x14001287f  jnz     short loc_14001288A
0x140012881  lea     rsi, aSifinalizespac; "SiFinalizeSpace"
0x140012888  jmp     short loc_1400128AD
0x14001288a  lea     rdx, [rdi+18h]; struct _GUID *
0x14001288e  mov     r8, r12; struct _SU_SPACE_OBJECT **
0x140012891  mov     rcx, r14; struct _SU_POOL_OBJECT *
0x140012894  xor     r15d, r15d
0x140012897  call    ?SuGetSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@PEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpace(_SU_POOL_OBJECT *,_GUID *,_SU_SPACE_OBJECT * *)
0x14001289c  mov     ebx, eax
0x14001289e  lea     rsi, aSugetspace; "SuGetSpace"
0x1400128a5  xor     eax, eax
0x1400128a7  test    ebx, ebx
0x1400128a9  cmovnz  rsi, rax
0x1400128ad  lea     rcx, [rbp+4Fh+var_68]; lpPerformanceCount
0x1400128b1  call    cs:__imp_QueryPerformanceCounter
0x1400128b7  test    ebx, ebx
0x1400128b9  jz      short loc_14001290F
0x1400128bb  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x1400128c2  jz      loc_140012952
0x1400128c8  mov     rax, qword ptr [rbp+4Fh+var_68]
0x1400128cc  lea     r8, [rdi+18h]
0x1400128d0  sub     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x1400128d4  lea     r9, [r14+28h]
0x1400128d8  movzx   ecx, byte ptr [rdi+0A28h]
0x1400128df  imul    rax, 0F4240h
0x1400128e6  cqo
0x1400128e8  idiv    [rbp+4Fh+var_60]
0x1400128ec  lea     rdx, [rdi+28h]
0x1400128f0  mov     [rsp+0D0h+var_88], rax
0x1400128f5  mov     [rsp+0D0h+var_90], ecx
0x1400128f9  mov     [rsp+0D0h+var_98], rdx
0x1400128fe  mov     [rsp+0D0h+var_A0], r8
0x140012903  mov     [rsp+0D0h+var_A8], r9
0x140012908  call    McTemplateK0zsjjzqx_EventWriteTransfer
0x14001290d  jmp     short loc_140012952
0x14001290f  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x140012916  jz      short loc_140012952
0x140012918  call    cs:__imp_GetLastError
0x14001291e  movzx   ecx, byte ptr [rdi+0A28h]
0x140012925  lea     rdx, [rdi+28h]
0x140012929  mov     [rsp+0D0h+var_80], eax
0x14001292d  lea     r8, [rdi+18h]
0x140012931  mov     [rsp+0D0h+var_88], rsi
0x140012936  lea     r9, [r14+28h]
0x14001293a  mov     [rsp+0D0h+var_90], ecx
0x14001293e  mov     [rsp+0D0h+var_98], rdx
0x140012943  mov     [rsp+0D0h+var_A0], r8
0x140012948  mov     [rsp+0D0h+var_A8], r9
0x14001294d  call    McTemplateK0zsjjzqsq_EventWriteTransfer
0x140012952  test    r15d, r15d
0x140012955  jz      short loc_140012960
0x140012957  lea     rcx, [rdi+8]; lpInBuffer
0x14001295b  call    ?SiCleanupSpace@@YAXPEAU_SP_ID@@@Z; SiCleanupSpace(_SP_ID *)
0x140012960  mov     eax, ebx
0x140012962  add     rsp, 0A0h
0x140012969  pop     r15
0x14001296b  pop     r14
0x14001296d  pop     r12
0x14001296f  pop     rdi
0x140012970  pop     rsi
0x140012971  pop     rbx
0x140012972  pop     rbp
0x140012973  retn
```
