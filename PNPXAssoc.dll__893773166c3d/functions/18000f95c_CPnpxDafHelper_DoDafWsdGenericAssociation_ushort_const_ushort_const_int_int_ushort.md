# CPnpxDafHelper::DoDafWsdGenericAssociation(ushort const *,ushort const *,int,int,ushort *)

- ea: `0x18000f95c`
- end: `0x18000fc53`
- name: `?DoDafWsdGenericAssociation@CPnpxDafHelper@@QEAAJPEBG0HHPEAG@Z`
- size: `759`
- prototype: `__int64 __fastcall(CPnpxDafHelper *this, const unsigned __int16 *, const unsigned __int16 *, int, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180009c10`

## callees

- `0x1800019b0`
- `0x1800019d4`
- `0x18000f6cc`
- `0x18000f95c`
- `0x18000ff38`
- `0x180012dc2`
- `0x180012dce`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000fba2`
- `KERNEL32!WaitForSingleObject` at `0x18000fbd8`
- `KERNEL32!WaitForSingleObject` at `0x18000fba2`
- `KERNEL32!WaitForSingleObject` at `0x18000fbd8`
- `KERNEL32!CloseHandle` at `0x18000fc18`
- `KERNEL32!CloseHandle` at `0x18000fc18`
- `KERNEL32!ResetEvent` at `0x18000fbb2`
- `KERNEL32!ResetEvent` at `0x18000fbb2`
- `deviceassociation!DafStartWriteCeremonyData` at `0x18000fb89`
- `deviceassociation!DafStartWriteCeremonyData` at `0x18000fb89`
- `deviceassociation!DafCloseAssociationContext` at `0x18000fc32`
- `deviceassociation!DafCloseAssociationContext` at `0x18000fc32`
- `deviceassociation!DafStartFinalize` at `0x18000fbc6`
- `deviceassociation!DafStartFinalize` at `0x18000fbc6`
- `deviceassociation!DafSelectCeremony` at `0x18000f9f8`
- `deviceassociation!DafSelectCeremony` at `0x18000f9f8`
- `deviceassociation!DafCreateAssociationContext` at `0x18000f9dd`
- `deviceassociation!DafCreateAssociationContext` at `0x18000f9dd`

## pseudocode

```c
__int64 __fastcall CPnpxDafHelper::DoDafWsdGenericAssociation(
        CPnpxDafHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        unsigned __int16 *a6)
{
  __int64 v6; // rcx
  __int64 v9; // rdi
  unsigned int started; // ebx
  char *v11; // rsi
  const unsigned __int16 *v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // r12d
  char *v15; // rax
  unsigned __int16 *v16; // r8
  __int64 v17; // rdx
  unsigned __int16 *v18; // rax
  __int64 v19; // r9
  __int64 v20; // rax
  _WORD *v21; // r9
  __int64 v22; // rax
  _WORD *v23; // rcx
  __int64 v25; // [rsp+30h] [rbp-10h] BYREF
  void *Block; // [rsp+38h] [rbp-8h] BYREF
  struct _PNPX_DAF_CONTEXT *v27; // [rsp+70h] [rbp+30h] BYREF

  v6 = *(_QWORD *)this;
  Block = 0;
  v27 = 0;
  v25 = 0;
  v9 = 0;
  if ( !v6 )
    return (unsigned int)-2147467259;
  v11 = 0;
  started = DafConcatenateWithDelimiter(v6, a2, a3, &Block);
  if ( !started )
  {
    started = CreatePnpxDafContext(&v27);
    if ( !started )
    {
      started = DafCreateAssociationContext(Block, 0, 0, 0, &v25);
      if ( !started )
      {
        started = DafSelectCeremony(v25, &DAF_Ceremony_WsdGeneric);
        if ( !started )
        {
          if ( !a3 )
            goto LABEL_12;
          v12 = a3;
          v13 = 0x7FFFFFFF;
          do
          {
            if ( !*v12 )
              break;
            ++v12;
            --v13;
          }
          while ( v13 );
          started = v13 == 0 ? 0x80070057 : 0;
          v9 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
          if ( v13 )
          {
LABEL_12:
            v14 = 2 * v9 + 2082;
            v15 = (char *)operator new(v14);
            v11 = v15;
            if ( v15 )
            {
              memset_0(v15, 0, (unsigned int)(2 * v9 + 2082));
              *(_OWORD *)v11 = DAF_Ceremony_WsdGeneric;
              if ( a4 )
              {
                *((_DWORD *)v11 + 5) = 1;
                if ( a5 )
                  *((_DWORD *)v11 + 5) = 2;
              }
              if ( a3 )
              {
                *((_DWORD *)v11 + 519) = v9 + 1;
                memcpy_0(v11 + 2080, a3, 2 * v9 + 2);
              }
              v16 = a6;
              if ( !a6 )
                goto LABEL_30;
              v17 = 1024;
              v18 = a6;
              v19 = 1024;
              do
              {
                if ( !*v18 )
                  break;
                ++v18;
                --v19;
              }
              while ( v19 );
              started = v19 == 0 ? 0x80070057 : 0;
              v20 = (1024 - v19) & -(__int64)(v19 != 0);
              if ( v19 )
              {
                v21 = v11 + 28;
                *((_DWORD *)v11 + 6) = v20 + 1;
                v22 = 2147483646;
                do
                {
                  if ( !v22 )
                    break;
                  if ( !*v16 )
                    break;
                  *v21++ = *v16++;
                  --v22;
                  --v17;
                }
                while ( v17 );
                v23 = v21 - 1;
                started = v17 == 0 ? 0x8007007A : 0;
                if ( v17 )
                  v23 = v21;
                *v23 = 0;
                if ( v17 )
                {
LABEL_30:
                  v9 = (__int64)v27;
                  started = DafStartWriteCeremonyData(v25, v14, v11, RemoveCallback, v27);
                  if ( !started )
                  {
                    WaitForSingleObject(*(HANDLE *)v9, 0xFFFFFFFF);
                    started = *(_DWORD *)(v9 + 8);
                    if ( !started )
                    {
                      ResetEvent(*(HANDLE *)v9);
                      started = DafStartFinalize(v25, &FinalizeCallback, v9);
                      if ( !started )
                      {
                        WaitForSingleObject(*(HANDLE *)v9, 0xFFFFFFFF);
                        started = *(_DWORD *)(v9 + 8);
                      }
                    }
                  }
                  goto LABEL_36;
                }
              }
            }
            else
            {
              started = -2147024882;
            }
          }
        }
      }
    }
    v9 = (__int64)v27;
  }
LABEL_36:
  if ( Block )
    operator delete(Block);
  if ( v11 )
    operator delete(v11);
  if ( v9 )
  {
    if ( *(_QWORD *)v9 )
    {
      CloseHandle(*(HANDLE *)v9);
      *(_QWORD *)v9 = 0;
    }
    operator delete((void *)v9);
  }
  if ( v25 )
    DafCloseAssociationContext();
  return started;
}

```

## disassembly

```asm
0x18000f95c  mov     [rsp-28h+arg_8], rbx
0x18000f961  mov     [rsp-28h+arg_10], rsi
0x18000f966  push    rbp
0x18000f967  push    rdi
0x18000f968  push    r12
0x18000f96a  push    r13
0x18000f96c  push    r14
0x18000f96e  mov     rbp, rsp
0x18000f971  sub     rsp, 40h
0x18000f975  mov     rcx, [rcx]
0x18000f978  xor     r12d, r12d
0x18000f97b  mov     [rbp+Block], r12
0x18000f97f  mov     r13d, r9d
0x18000f982  mov     [rbp+arg_0], r12
0x18000f986  mov     r14, r8
0x18000f989  mov     [rbp+var_10], r12
0x18000f98d  mov     edi, r12d
0x18000f990  test    rcx, rcx
0x18000f993  jnz     short loc_18000F99F
0x18000f995  mov     ebx, 80004005h
0x18000f99a  jmp     loc_18000FC38
0x18000f99f  lea     r9, [rbp+Block]
0x18000f9a3  mov     rsi, r12
0x18000f9a6  call    DafConcatenateWithDelimiter
0x18000f9ab  mov     ebx, eax
0x18000f9ad  test    eax, eax
0x18000f9af  jnz     loc_18000FBEF
0x18000f9b5  lea     rcx, [rbp+arg_0]; struct _PNPX_DAF_CONTEXT **
0x18000f9b9  call    ?CreatePnpxDafContext@@YAJPEAPEAU_PNPX_DAF_CONTEXT@@@Z; CreatePnpxDafContext(_PNPX_DAF_CONTEXT * *)
0x18000f9be  mov     ebx, eax
0x18000f9c0  test    eax, eax
0x18000f9c2  jnz     loc_18000FBEB
0x18000f9c8  mov     rcx, [rbp+Block]
0x18000f9cc  lea     rax, [rbp+var_10]
0x18000f9d0  xor     r9d, r9d
0x18000f9d3  mov     [rsp+40h+var_20], rax
0x18000f9d8  xor     r8d, r8d
0x18000f9db  xor     edx, edx
0x18000f9dd  call    cs:__imp_DafCreateAssociationContext
0x18000f9e3  mov     ebx, eax
0x18000f9e5  test    eax, eax
0x18000f9e7  jnz     loc_18000FBEB
0x18000f9ed  mov     rcx, [rbp+var_10]
0x18000f9f1  lea     rdx, DAF_Ceremony_WsdGeneric
0x18000f9f8  call    cs:__imp_DafSelectCeremony
0x18000f9fe  mov     ebx, eax
0x18000fa00  test    eax, eax
0x18000fa02  jnz     loc_18000FBEB
0x18000fa08  test    r14, r14
0x18000fa0b  jz      short loc_18000FA4F
0x18000fa0d  mov     edx, 7FFFFFFFh
0x18000fa12  mov     rax, r14
0x18000fa15  mov     ecx, edx
0x18000fa17  cmp     [rax], r12w
0x18000fa1b  jz      short loc_18000FA27
0x18000fa1d  add     rax, 2
0x18000fa21  sub     rcx, 1
0x18000fa25  jnz     short loc_18000FA17
0x18000fa27  mov     rax, rcx
0x18000fa2a  neg     rax
0x18000fa2d  mov     rax, rcx
0x18000fa30  sbb     ebx, ebx
0x18000fa32  sub     rdx, rcx
0x18000fa35  not     ebx
0x18000fa37  and     ebx, 80070057h
0x18000fa3d  neg     rax
0x18000fa40  sbb     rdi, rdi
0x18000fa43  and     rdi, rdx
0x18000fa46  test    rcx, rcx
0x18000fa49  jz      loc_18000FBEB
0x18000fa4f  lea     r12d, ds:822h[rdi*2]
0x18000fa57  mov     ecx, r12d; Size
0x18000fa5a  mov     ebx, r12d
0x18000fa5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fa62  mov     rsi, rax
0x18000fa65  test    rax, rax
0x18000fa68  jz      loc_18000FBE3
0x18000fa6e  mov     r8d, ebx; Size
0x18000fa71  xor     edx, edx; Val
0x18000fa73  mov     rcx, rax; void *
0x18000fa76  call    memset_0
0x18000fa7b  movups  xmm0, cs:DAF_Ceremony_WsdGeneric
0x18000fa82  xor     r10d, r10d
0x18000fa85  movdqu  xmmword ptr [rsi], xmm0
0x18000fa89  test    r13d, r13d
0x18000fa8c  jz      short loc_18000FAA2
0x18000fa8e  mov     dword ptr [rsi+14h], 1
0x18000fa95  cmp     [rbp+arg_20], r10d
0x18000fa99  jz      short loc_18000FAA2
0x18000fa9b  mov     dword ptr [rsi+14h], 2
0x18000faa2  test    r14, r14
0x18000faa5  jz      short loc_18000FACA
0x18000faa7  lea     eax, [rdi+1]
0x18000faaa  mov     rdx, r14; Src
0x18000faad  lea     r8, ds:2[rdi*2]; Size
0x18000fab5  mov     [rsi+81Ch], eax
0x18000fabb  lea     rcx, [rsi+820h]; void *
0x18000fac2  call    memcpy_0
0x18000fac7  xor     r10d, r10d
0x18000faca  mov     r8, [rbp+arg_28]
0x18000face  test    r8, r8
0x18000fad1  jz      loc_18000FB6F
0x18000fad7  mov     edx, 400h
0x18000fadc  mov     rax, r8
0x18000fadf  mov     r9d, edx
0x18000fae2  cmp     [rax], r10w
0x18000fae6  jz      short loc_18000FAF2
0x18000fae8  add     rax, 2
0x18000faec  sub     r9, 1
0x18000faf0  jnz     short loc_18000FAE2
0x18000faf2  mov     rax, r9
0x18000faf5  mov     rcx, rdx
0x18000faf8  neg     rax
0x18000fafb  mov     rax, r9
0x18000fafe  sbb     ebx, ebx
0x18000fb00  sub     rcx, r9
0x18000fb03  not     ebx
0x18000fb05  and     ebx, 80070057h
0x18000fb0b  neg     rax
0x18000fb0e  sbb     rax, rax
0x18000fb11  and     rax, rcx
0x18000fb14  test    r9, r9
0x18000fb17  jz      loc_18000FBE8
0x18000fb1d  inc     eax
0x18000fb1f  lea     r9, [rsi+1Ch]
0x18000fb23  mov     [rsi+18h], eax
0x18000fb26  mov     eax, 7FFFFFFEh
0x18000fb2b  test    rax, rax
0x18000fb2e  jz      short loc_18000FB4E
0x18000fb30  movzx   ecx, word ptr [r8]
0x18000fb34  test    cx, cx
0x18000fb37  jz      short loc_18000FB4E
0x18000fb39  mov     [r9], cx
0x18000fb3d  add     r8, 2
0x18000fb41  add     r9, 2
0x18000fb45  dec     rax
0x18000fb48  sub     rdx, 1
0x18000fb4c  jnz     short loc_18000FB2B
0x18000fb4e  mov     rax, rdx
0x18000fb51  lea     rcx, [r9-2]
0x18000fb55  neg     rax
0x18000fb58  sbb     ebx, ebx
0x18000fb5a  not     ebx
0x18000fb5c  and     ebx, 8007007Ah
0x18000fb62  test    rdx, rdx
0x18000fb65  cmovnz  rcx, r9
0x18000fb69  mov     [rcx], r10w
0x18000fb6d  jz      short loc_18000FBE8
0x18000fb6f  mov     rdi, [rbp+arg_0]
0x18000fb73  lea     r9, ?RemoveCallback@@YAXPEAXJ@Z; RemoveCallback(void *,long)
0x18000fb7a  mov     rcx, [rbp+var_10]
0x18000fb7e  mov     r8, rsi
0x18000fb81  mov     edx, r12d
0x18000fb84  mov     [rsp+40h+var_20], rdi
0x18000fb89  call    cs:__imp_DafStartWriteCeremonyData
0x18000fb8f  xor     r12d, r12d
0x18000fb92  mov     ebx, eax
0x18000fb94  test    eax, eax
0x18000fb96  jnz     short loc_18000FBEF
0x18000fb98  mov     rcx, [rdi]; hHandle
0x18000fb9b  or      r14d, 0FFFFFFFFh
0x18000fb9f  mov     edx, r14d; dwMilliseconds
0x18000fba2  call    cs:__imp_WaitForSingleObject
0x18000fba8  mov     ebx, [rdi+8]
0x18000fbab  test    ebx, ebx
0x18000fbad  jnz     short loc_18000FBEF
0x18000fbaf  mov     rcx, [rdi]; hEvent
0x18000fbb2  call    cs:__imp_ResetEvent
0x18000fbb8  mov     rcx, [rbp+var_10]
0x18000fbbc  lea     rdx, ?FinalizeCallback@@YAXW4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; FinalizeCallback(_DAF_ASSOCIATION_STATUS,void *,long)
0x18000fbc3  mov     r8, rdi
0x18000fbc6  call    cs:__imp_DafStartFinalize
0x18000fbcc  mov     ebx, eax
0x18000fbce  test    eax, eax
0x18000fbd0  jnz     short loc_18000FBEF
0x18000fbd2  mov     rcx, [rdi]; hHandle
0x18000fbd5  mov     edx, r14d; dwMilliseconds
0x18000fbd8  call    cs:__imp_WaitForSingleObject
0x18000fbde  mov     ebx, [rdi+8]
0x18000fbe1  jmp     short loc_18000FBEF
0x18000fbe3  mov     ebx, 8007000Eh
0x18000fbe8  xor     r12d, r12d
0x18000fbeb  mov     rdi, [rbp+arg_0]
0x18000fbef  cmp     [rbp+Block], r12
0x18000fbf3  jz      short loc_18000FBFE
0x18000fbf5  mov     rcx, [rbp+Block]; Block
0x18000fbf9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fbfe  test    rsi, rsi
0x18000fc01  jz      short loc_18000FC0B
0x18000fc03  mov     rcx, rsi; Block
0x18000fc06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fc0b  test    rdi, rdi
0x18000fc0e  jz      short loc_18000FC29
0x18000fc10  mov     rcx, [rdi]; hObject
0x18000fc13  test    rcx, rcx
0x18000fc16  jz      short loc_18000FC21
0x18000fc18  call    cs:__imp_CloseHandle
0x18000fc1e  mov     [rdi], r12
0x18000fc21  mov     rcx, rdi; Block
0x18000fc24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fc29  mov     rcx, [rbp+var_10]
0x18000fc2d  test    rcx, rcx
0x18000fc30  jz      short loc_18000FC38
0x18000fc32  call    cs:__imp_DafCloseAssociationContext
0x18000fc38  lea     r11, [rsp+40h+var_s0]
0x18000fc3d  mov     eax, ebx
0x18000fc3f  mov     rbx, [r11+38h]
0x18000fc43  mov     rsi, [r11+40h]
0x18000fc47  mov     rsp, r11
0x18000fc4a  pop     r14
0x18000fc4c  pop     r13
0x18000fc4e  pop     r12
0x18000fc50  pop     rdi
0x18000fc51  pop     rbp
0x18000fc52  retn
```
