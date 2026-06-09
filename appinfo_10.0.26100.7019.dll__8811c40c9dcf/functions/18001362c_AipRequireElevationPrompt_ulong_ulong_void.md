# AipRequireElevationPrompt(ulong,ulong *,void *)

- ea: `0x18001362c`
- end: `0x18001370e`
- name: `?AipRequireElevationPrompt@@YAJKPEAKPEAX@Z`
- size: `226`
- prototype: `int(unsigned int, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016c54`

## callees

- `0x180011eb8`
- `0x18001362c`
- `0x1800168f0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180013681`
- `ntdll!NtQueryInformationToken` at `0x180013681`

## pseudocode

```c
__int64 __fastcall AipRequireElevationPrompt(int a1, unsigned int *a2, void *a3)
{
  NTSTATUS v5; // edx
  int v7; // eax
  ULONG ReturnLength[6]; // [rsp+30h] [rbp-18h] BYREF
  int v10; // [rsp+50h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  v10 = 0;
  TokenInformation = 0;
  ReturnLength[0] = 0;
  v7 = *a2;
  if ( !a1 )
  {
    *a2 = v7 | 0x10;
    return (unsigned int)v5;
  }
  if ( (v7 & 0x2000000) != 0 )
    goto LABEL_14;
  v5 = NtQueryInformationToken(a3, TokenElevationType, &TokenInformation, 4u, ReturnLength);
  if ( v5 < 0 )
    return (unsigned int)v5;
  if ( TokenInformation == 2 )
  {
LABEL_6:
    *a2 |= 0x10u;
    return (unsigned int)v5;
  }
  if ( TokenInformation != 1 )
  {
    if ( a1 == 1 )
      *a2 |= 0x200u;
LABEL_14:
    v5 = AiCheckForAdminUser(a3, (*a2 >> 25) & 1, &v10);
    if ( v5 >= 0 )
      *a2 |= v10 != 0 ? 32 : 64;
    return (unsigned int)v5;
  }
  if ( a1 == 1 )
    goto LABEL_6;
  v5 = AiCheckForElevatedUser(a3, &v10);
  if ( v5 >= 0 )
  {
    if ( v10 )
      goto LABEL_6;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001362c  mov     rax, rsp
0x18001362f  mov     [rax+10h], rbx
0x180013633  mov     [rax+18h], rsi
0x180013637  push    rdi
0x180013638  sub     rsp, 40h
0x18001363c  mov     rbx, rdx
0x18001363f  mov     rsi, r8
0x180013642  xor     edx, edx
0x180013644  mov     edi, ecx
0x180013646  and     [rax+8], edx
0x180013649  and     [rax+20h], edx
0x18001364c  and     [rax-18h], edx
0x18001364f  mov     eax, [rbx]
0x180013651  test    ecx, ecx
0x180013653  jnz     short loc_18001365F
0x180013655  or      eax, 10h
0x180013658  mov     [rbx], eax
0x18001365a  jmp     loc_1800136FB
0x18001365f  bt      eax, 19h
0x180013663  jb      short loc_1800136D0
0x180013665  mov     r9d, 4; TokenInformationLength
0x18001366b  lea     rax, [rsp+48h+var_18]
0x180013670  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180013675  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001367a  mov     rcx, rsi; TokenHandle
0x18001367d  lea     edx, [r9+0Eh]; TokenInformationClass
0x180013681  call    cs:__imp_NtQueryInformationToken
0x180013688  nop     dword ptr [rax+rax+00h]
0x18001368d  mov     edx, eax
0x18001368f  test    eax, eax
0x180013691  js      short loc_1800136FB
0x180013693  cmp     [rsp+48h+TokenInformation], 2
0x180013698  jnz     short loc_18001369F
0x18001369a  or      dword ptr [rbx], 10h
0x18001369d  jmp     short loc_1800136FB
0x18001369f  cmp     [rsp+48h+TokenInformation], 1
0x1800136a4  jnz     short loc_1800136C7
0x1800136a6  cmp     edi, 1
0x1800136a9  jz      short loc_18001369A
0x1800136ab  lea     rdx, [rsp+48h+arg_0]; int *
0x1800136b0  mov     rcx, rsi; void *
0x1800136b3  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x1800136b8  mov     edx, eax
0x1800136ba  test    eax, eax
0x1800136bc  js      short loc_1800136FB
0x1800136be  cmp     [rsp+48h+arg_0], 0
0x1800136c3  jz      short loc_1800136FB
0x1800136c5  jmp     short loc_18001369A
0x1800136c7  cmp     edi, 1
0x1800136ca  jnz     short loc_1800136D0
0x1800136cc  bts     dword ptr [rbx], 9
0x1800136d0  mov     edx, [rbx]
0x1800136d2  lea     r8, [rsp+48h+arg_0]; int *
0x1800136d7  shr     edx, 19h
0x1800136da  mov     rcx, rsi; Handle
0x1800136dd  and     edx, 1; int
0x1800136e0  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x1800136e5  mov     edx, eax
0x1800136e7  test    eax, eax
0x1800136e9  js      short loc_1800136FB
0x1800136eb  mov     eax, [rsp+48h+arg_0]
0x1800136ef  neg     eax
0x1800136f1  sbb     ecx, ecx
0x1800136f3  and     ecx, 0FFFFFFE0h
0x1800136f6  add     ecx, 40h ; '@'
0x1800136f9  or      [rbx], ecx
0x1800136fb  mov     rbx, [rsp+48h+arg_8]
0x180013700  mov     eax, edx
0x180013702  mov     rsi, [rsp+48h+arg_10]
0x180013707  add     rsp, 40h
0x18001370b  pop     rdi
0x18001370c  retn
```
