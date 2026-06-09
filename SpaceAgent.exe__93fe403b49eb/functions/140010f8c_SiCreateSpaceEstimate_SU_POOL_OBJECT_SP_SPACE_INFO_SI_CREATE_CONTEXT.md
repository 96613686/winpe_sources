# SiCreateSpaceEstimate(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SI_CREATE_CONTEXT *)

- ea: `0x140010f8c`
- end: `0x1400111bc`
- name: `?SiCreateSpaceEstimate@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@PEAU_SI_CREATE_CONTEXT@@@Z`
- size: `560`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, struct _SI_CREATE_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140010b5c`

## callees

- `0x14000fea0`
- `0x140010f8c`
- `0x1400111c4`
- `0x140011910`
- `0x140011a74`
- `0x140011edc`
- `0x140012164`
- `0x140013e1c`
- `0x140013e84`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140011089`
- `KERNEL32!SetLastError` at `0x140011089`
- `KERNEL32!GetLastError` at `0x140011137`
- `KERNEL32!GetLastError` at `0x140011137`

## pseudocode

```c
__int64 __fastcall SiCreateSpaceEstimate(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        struct _SI_CREATE_CONTEXT *a3)
{
  char *v6; // r12
  unsigned int SpaceInternal; // esi
  unsigned int v8; // edx
  __int64 i; // r15
  unsigned int v10; // ebx
  bool v11; // zf
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  int v15; // [rsp+20h] [rbp-50h]
  __int64 v16; // [rsp+28h] [rbp-48h]
  __int128 v17; // [rsp+30h] [rbp-40h] BYREF
  __int128 v18; // [rsp+40h] [rbp-30h]
  __int128 v19; // [rsp+50h] [rbp-20h]
  __int64 v20; // [rsp+60h] [rbp-10h]

  v16 = *((_QWORD *)a2 + 333);
  v20 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( a3 )
  {
    *(_OWORD *)a3 = 0;
    *((_OWORD *)a3 + 1) = 0;
    *((_OWORD *)a3 + 2) = 0;
    *((_QWORD *)a3 + 6) = 0;
  }
  v6 = (char *)a2 + 2748;
  LODWORD(v17) = 1;
  *((_QWORD *)&v17 + 1) = (char *)a2 + 2696;
  *(_QWORD *)&v18 = (char *)a2 + 2748;
  SpaceInternal = SiFixupProvisioning(a1, (struct _SI_CREATE_CONTEXT *)&v17);
  if ( SpaceInternal )
  {
    SpaceInternal = SiFixupResiliency(a1, (struct _SI_CREATE_CONTEXT *)&v17);
    if ( SpaceInternal )
    {
      SpaceInternal = SiValidateSpace(a1, a2, 1u);
      if ( SpaceInternal )
      {
        if ( *((_QWORD *)a2 + 333) == -1 )
          *((_QWORD *)a2 + 333) = 1;
        v8 = HIDWORD(v20);
        for ( i = 0; (unsigned int)i < DWORD2(v18); i = (unsigned int)(i + 1) )
        {
          v10 = v20;
          *((_DWORD *)a2 + 678) = *((_DWORD *)&v18 + i + 3);
          while ( v10 >= v8 )
          {
            SetLastError(0);
            v11 = (v17 & 2) == 0;
            *((_DWORD *)a2 + 691) = v10;
            if ( !v11 )
              SP_RESILIENCY_INFO::SetNumberOfGroups(v6, *((unsigned int *)a2 + 678));
            if ( *((_DWORD *)a2 + 691) > HIDWORD(v20) )
              SP_RESILIENCY_INFO::SetNumberOfColumns(v6, *((unsigned int *)a2 + 678));
            v15 = *((_DWORD *)a2 + 691);
            if ( ((*((_BYTE *)a2 + 2600) - 3) & 0xFD) == 0 )
              *((_QWORD *)a2 + 338) = *((unsigned int *)a2 + 691)
                                    * *((_QWORD *)a1 + 342)
                                    * (((unsigned __int64)*((unsigned int *)a2 + 691) * *((_QWORD *)a1 + 342)
                                      + *((_QWORD *)a2 + 333)
                                      - 1LL)
                                     / ((unsigned __int64)*((unsigned int *)a2 + 691)
                                      * *((_QWORD *)a1 + 342)))
                                    / *((unsigned int *)a2 + 691);
            SpaceInternal = SiCreateSpaceInternal(a1, a2);
            if ( !SpaceInternal )
              goto LABEL_27;
            SpaceInternal = SiGrowSpace((struct _SP_SPACE_INFO *)((char *)a2 + 8));
            SiCleanupSpace((struct _SP_SPACE_INFO *)((char *)a2 + 8));
            if ( SpaceInternal )
              goto LABEL_25;
            if ( GetLastError() != 314 )
              goto LABEL_27;
            v8 = HIDWORD(v20);
            v10 = v15 - 1;
          }
          if ( SpaceInternal )
            goto LABEL_25;
        }
        if ( !SpaceInternal )
          goto LABEL_27;
LABEL_25:
        if ( a3 )
        {
          v12 = v18;
          *(_OWORD *)a3 = v17;
          v13 = v19;
          *((_OWORD *)a3 + 1) = v12;
          *(_QWORD *)&v12 = v20;
          *((_OWORD *)a3 + 2) = v13;
          *((_QWORD *)a3 + 6) = v12;
        }
      }
    }
  }
LABEL_27:
  *((_QWORD *)a2 + 333) = v16;
  return SpaceInternal;
}

```

## disassembly

```asm
0x140010f8c  mov     [rsp-38h+arg_18], rbx
0x140010f91  push    rbp
0x140010f92  push    rsi
0x140010f93  push    rdi
0x140010f94  push    r12
0x140010f96  push    r13
0x140010f98  push    r14
0x140010f9a  push    r15
0x140010f9c  mov     rbp, rsp
0x140010f9f  sub     rsp, 70h
0x140010fa3  mov     rax, cs:__security_cookie
0x140010faa  xor     rax, rsp
0x140010fad  mov     [rbp+var_8], rax
0x140010fb1  mov     rax, [rdx+0A68h]
0x140010fb8  xorps   xmm0, xmm0
0x140010fbb  mov     [rbp+var_48], rax
0x140010fbf  mov     r14, r8
0x140010fc2  xor     eax, eax
0x140010fc4  mov     rdi, rdx
0x140010fc7  mov     [rbp+var_10], rax
0x140010fcb  mov     r13, rcx
0x140010fce  movups  [rbp+var_40], xmm0
0x140010fd2  movups  [rbp+var_30], xmm0
0x140010fd6  movups  [rbp+var_20], xmm0
0x140010fda  test    r8, r8
0x140010fdd  jz      short loc_140010FF1
0x140010fdf  movups  xmmword ptr [r8], xmm0
0x140010fe3  movups  xmmword ptr [r8+10h], xmm0
0x140010fe8  movups  xmmword ptr [r8+20h], xmm0
0x140010fed  mov     [r8+30h], rax
0x140010ff1  lea     rax, [rdx+0A88h]
0x140010ff8  mov     ebx, 1
0x140010ffd  lea     r12, [rdx+0ABCh]
0x140011004  mov     dword ptr [rbp+var_40], ebx
0x140011007  lea     rdx, [rbp+var_40]; struct _SI_CREATE_CONTEXT *
0x14001100b  mov     qword ptr [rbp+var_40+8], rax
0x14001100f  mov     qword ptr [rbp+var_30], r12
0x140011013  call    ?SiFixupProvisioning@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SI_CREATE_CONTEXT@@@Z; SiFixupProvisioning(_SU_POOL_OBJECT *,_SI_CREATE_CONTEXT *)
0x140011018  mov     esi, eax
0x14001101a  test    eax, eax
0x14001101c  jz      loc_14001118B
0x140011022  lea     rdx, [rbp+var_40]; struct _SI_CREATE_CONTEXT *
0x140011026  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140011029  call    ?SiFixupResiliency@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SI_CREATE_CONTEXT@@@Z; SiFixupResiliency(_SU_POOL_OBJECT *,_SI_CREATE_CONTEXT *)
0x14001102e  mov     esi, eax
0x140011030  test    eax, eax
0x140011032  jz      loc_14001118B
0x140011038  mov     r8b, bl; unsigned __int8
0x14001103b  mov     rdx, rdi; struct _SP_SPACE_INFO *
0x14001103e  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140011041  call    ?SiValidateSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@E@Z; SiValidateSpace(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,uchar)
0x140011046  mov     esi, eax
0x140011048  test    eax, eax
0x14001104a  jz      loc_14001118B
0x140011050  cmp     qword ptr [rdi+0A68h], 0FFFFFFFFFFFFFFFFh
0x140011058  jnz     short loc_140011061
0x14001105a  mov     [rdi+0A68h], rbx
0x140011061  mov     edx, dword ptr [rbp+var_10+4]
0x140011064  xor     r15d, r15d
0x140011067  cmp     r15d, dword ptr [rbp+var_30+8]
0x14001106b  jnb     loc_14001115D
0x140011071  mov     ecx, dword ptr [rbp+r15*4+var_30+0Ch]
0x140011076  mov     ebx, dword ptr [rbp+var_10]
0x140011079  mov     [rdi+0A98h], ecx
0x14001107f  cmp     ebx, edx
0x140011081  jb      loc_140011151
0x140011087  xor     ecx, ecx; dwErrCode
0x140011089  call    cs:__imp_SetLastError
0x14001108f  test    byte ptr [rbp+var_40], 2
0x140011093  mov     [rdi+0ACCh], ebx
0x140011099  jz      short loc_1400110A9
0x14001109b  mov     edx, [rdi+0A98h]
0x1400110a1  mov     rcx, r12
0x1400110a4  call    ?SetNumberOfGroups@SP_RESILIENCY_INFO@@QEAAXW4_SC_MEDIA_TYPE@@@Z; SP_RESILIENCY_INFO::SetNumberOfGroups(_SC_MEDIA_TYPE)
0x1400110a9  mov     eax, dword ptr [rbp+var_10+4]
0x1400110ac  cmp     [rdi+0ACCh], eax
0x1400110b2  jbe     short loc_1400110C2
0x1400110b4  mov     edx, [rdi+0A98h]
0x1400110ba  mov     rcx, r12
0x1400110bd  call    ?SetNumberOfColumns@SP_RESILIENCY_INFO@@QEAAXW4_SC_MEDIA_TYPE@@@Z; SP_RESILIENCY_INFO::SetNumberOfColumns(_SC_MEDIA_TYPE)
0x1400110c2  mov     al, [rdi+0A28h]
0x1400110c8  mov     ecx, [rdi+0ACCh]
0x1400110ce  sub     al, 3
0x1400110d0  mov     [rbp+var_50], ecx
0x1400110d3  test    al, 0FDh
0x1400110d5  jnz     short loc_14001110E
0x1400110d7  mov     r8, [r13+0AB0h]
0x1400110de  mov     r9d, ecx
0x1400110e1  mov     rax, [rdi+0A68h]
0x1400110e8  xor     edx, edx
0x1400110ea  dec     rax
0x1400110ed  mov     rcx, r8
0x1400110f0  imul    rcx, r9
0x1400110f4  add     rax, rcx
0x1400110f7  div     rcx
0x1400110fa  xor     edx, edx
0x1400110fc  imul    rax, r8
0x140011100  imul    rax, r9
0x140011104  div     r9
0x140011107  mov     [rdi+0A90h], rax
0x14001110e  mov     rdx, rdi; struct _SP_SPACE_INFO *
0x140011111  mov     rcx, r13; struct _SU_POOL_OBJECT *
0x140011114  call    ?SiCreateSpaceInternal@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@@Z; SiCreateSpaceInternal(_SU_POOL_OBJECT *,_SP_SPACE_INFO *)
0x140011119  mov     esi, eax
0x14001111b  test    eax, eax
0x14001111d  jz      short loc_14001118B
0x14001111f  lea     rcx, [rdi+8]; lpInBuffer
0x140011123  call    ?SiGrowSpace@@YAHPEAU_SP_ID@@@Z; SiGrowSpace(_SP_ID *)
0x140011128  lea     rcx, [rdi+8]; lpInBuffer
0x14001112c  mov     esi, eax
0x14001112e  call    ?SiCleanupSpace@@YAXPEAU_SP_ID@@@Z; SiCleanupSpace(_SP_ID *)
0x140011133  test    esi, esi
0x140011135  jnz     short loc_140011161
0x140011137  call    cs:__imp_GetLastError
0x14001113d  cmp     eax, 13Ah
0x140011142  jnz     short loc_14001118B
0x140011144  mov     ebx, [rbp+var_50]
0x140011147  mov     edx, dword ptr [rbp+var_10+4]
0x14001114a  dec     ebx
0x14001114c  jmp     loc_14001107F
0x140011151  test    esi, esi
0x140011153  jnz     short loc_140011161
0x140011155  inc     r15d
0x140011158  jmp     loc_140011067
0x14001115d  test    esi, esi
0x14001115f  jz      short loc_14001118B
0x140011161  test    r14, r14
0x140011164  jz      short loc_14001118B
0x140011166  movups  xmm0, [rbp+var_40]
0x14001116a  movups  xmm1, [rbp+var_30]
0x14001116e  movups  xmmword ptr [r14], xmm0
0x140011172  movups  xmm0, [rbp+var_20]
0x140011176  movups  xmmword ptr [r14+10h], xmm1
0x14001117b  movsd   xmm1, [rbp+var_10]
0x140011180  movups  xmmword ptr [r14+20h], xmm0
0x140011185  movsd   qword ptr [r14+30h], xmm1
0x14001118b  mov     rax, [rbp+var_48]
0x14001118f  mov     [rdi+0A68h], rax
0x140011196  mov     eax, esi
0x140011198  mov     rcx, [rbp+var_8]
0x14001119c  xor     rcx, rsp; StackCookie
0x14001119f  call    __security_check_cookie
0x1400111a4  mov     rbx, [rsp+70h+arg_18]
0x1400111ac  add     rsp, 70h
0x1400111b0  pop     r15
0x1400111b2  pop     r14
0x1400111b4  pop     r13
0x1400111b6  pop     r12
0x1400111b8  pop     rdi
0x1400111b9  pop     rsi
0x1400111ba  pop     rbp
0x1400111bb  retn
```
