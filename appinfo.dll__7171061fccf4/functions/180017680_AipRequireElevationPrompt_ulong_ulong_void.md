# AipRequireElevationPrompt(ulong,ulong *,void *)

- ea: `0x180017680`
- end: `0x18001779b`
- name: `?AipRequireElevationPrompt@@YAJKPEAKPEAX@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003f14c`

## callees

- `0x180010dd4`
- `0x180017680`
- `0x18003ef28`
- `0x1800461e8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800176f9`
- `ntdll!NtQueryInformationToken` at `0x1800176f9`

## pseudocode

```c
__int64 __fastcall AipRequireElevationPrompt(__int64 a1, unsigned int *a2, void *a3)
{
  unsigned int v5; // esi
  NTSTATUS v6; // edi
  int v7; // eax
  int TokenInformation; // [rsp+30h] [rbp-38h] BYREF
  ULONG ReturnLength[13]; // [rsp+34h] [rbp-34h] BYREF
  int v11; // [rsp+88h] [rbp+20h] BYREF

  v11 = 0;
  TokenInformation = 0;
  v5 = a1;
  ReturnLength[0] = 0;
  if ( !(_DWORD)a1 )
  {
    *a2 |= 0x10u;
    v6 = 0;
    if ( !(unsigned int)LUAIsShadowAdminEnabled(a1) || (*a2 & 0x40000004) != 4 )
      return (unsigned int)v6;
    *a2 &= ~0x10u;
  }
  if ( (*a2 & 0x2000000) != 0 )
    goto LABEL_16;
  v6 = NtQueryInformationToken(a3, TokenElevationType, &TokenInformation, 4u, ReturnLength);
  if ( v6 < 0 )
    return (unsigned int)v6;
  if ( TokenInformation == 2 )
  {
LABEL_8:
    *a2 |= 0x10u;
    return (unsigned int)v6;
  }
  if ( TokenInformation != 1 )
  {
    if ( v5 == 1 )
      *a2 |= 0x200u;
LABEL_16:
    v6 = AiCheckForAdminUser(a3, (*a2 >> 25) & 1, &v11);
    if ( v6 >= 0 )
    {
      *a2 |= v11 != 0 ? 32 : 64;
      v7 = *a2;
      if ( !v5 && (v7 & 0x40) != 0 )
        *a2 = v7 | 0x10;
    }
    return (unsigned int)v6;
  }
  if ( v5 < 2 )
    goto LABEL_8;
  v6 = AiCheckForElevatedUser(a3, &v11);
  if ( v6 >= 0 )
  {
    if ( v11 )
      goto LABEL_8;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017680  mov     rax, rsp
0x180017683  push    rbx
0x180017684  push    rbp
0x180017685  push    rsi
0x180017686  push    rdi
0x180017687  sub     rsp, 48h
0x18001768b  mov     rbp, r8
0x18001768e  mov     dword ptr [rax+20h], 0
0x180017695  mov     rbx, rdx
0x180017698  mov     dword ptr [rax-38h], 0
0x18001769f  mov     esi, ecx
0x1800176a1  mov     dword ptr [rax-34h], 0
0x1800176a8  test    ecx, ecx
0x1800176aa  jnz     short loc_1800176D5
0x1800176ac  or      dword ptr [rdx], 10h
0x1800176af  xor     edi, edi
0x1800176b1  call    LUAIsShadowAdminEnabled
0x1800176b6  test    eax, eax
0x1800176b8  jz      loc_180017790
0x1800176be  mov     ecx, [rbx]
0x1800176c0  mov     eax, ecx
0x1800176c2  and     eax, 40000004h
0x1800176c7  cmp     eax, 4
0x1800176ca  jnz     loc_180017790
0x1800176d0  and     ecx, 0FFFFFFEFh
0x1800176d3  mov     [rbx], ecx
0x1800176d5  test    dword ptr [rbx], 2000000h
0x1800176db  jnz     short loc_180017750
0x1800176dd  mov     r9d, 4; TokenInformationLength
0x1800176e3  lea     rax, [rsp+68h+var_34]
0x1800176e8  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x1800176ed  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800176f2  mov     rcx, rbp; TokenHandle
0x1800176f5  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800176f9  call    cs:__imp_NtQueryInformationToken
0x1800176ff  mov     edi, eax
0x180017701  test    eax, eax
0x180017703  js      loc_180017790
0x180017709  cmp     [rsp+68h+TokenInformation], 2
0x18001770e  jnz     short loc_180017715
0x180017710  or      dword ptr [rbx], 10h
0x180017713  jmp     short loc_180017790
0x180017715  cmp     [rsp+68h+TokenInformation], 1
0x18001771a  jnz     short loc_180017747
0x18001771c  test    esi, esi
0x18001771e  jz      short loc_180017710
0x180017720  cmp     esi, 1
0x180017723  jz      short loc_180017710
0x180017725  lea     rdx, [rsp+68h+arg_18]; int *
0x18001772d  mov     rcx, rbp; void *
0x180017730  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x180017735  mov     edi, eax
0x180017737  test    eax, eax
0x180017739  js      short loc_180017790
0x18001773b  cmp     [rsp+68h+arg_18], 0
0x180017743  jz      short loc_180017790
0x180017745  jmp     short loc_180017710
0x180017747  cmp     esi, 1
0x18001774a  jnz     short loc_180017750
0x18001774c  bts     dword ptr [rbx], 9
0x180017750  mov     edx, [rbx]
0x180017752  lea     r8, [rsp+68h+arg_18]; int *
0x18001775a  shr     edx, 19h
0x18001775d  mov     rcx, rbp; Handle
0x180017760  and     edx, 1; int
0x180017763  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x180017768  mov     edi, eax
0x18001776a  test    eax, eax
0x18001776c  js      short loc_180017790
0x18001776e  mov     eax, [rsp+68h+arg_18]
0x180017775  neg     eax
0x180017777  sbb     ecx, ecx
0x180017779  and     ecx, 0FFFFFFE0h
0x18001777c  add     ecx, 40h ; '@'
0x18001777f  or      [rbx], ecx
0x180017781  mov     eax, [rbx]
0x180017783  test    esi, esi
0x180017785  jnz     short loc_180017790
0x180017787  test    al, 40h
0x180017789  jz      short loc_180017790
0x18001778b  or      eax, 10h
0x18001778e  mov     [rbx], eax
0x180017790  mov     eax, edi
0x180017792  add     rsp, 48h
0x180017796  pop     rdi
0x180017797  pop     rsi
0x180017798  pop     rbp
0x180017799  pop     rbx
0x18001779a  retn
```
