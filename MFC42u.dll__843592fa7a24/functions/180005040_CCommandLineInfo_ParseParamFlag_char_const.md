# CCommandLineInfo::ParseParamFlag(char const *)

- ea: `0x180005040`
- end: `0x1800051c4`
- name: `?ParseParamFlag@CCommandLineInfo@@IEAAXPEBD@Z`
- size: `388`
- prototype: `void(CCommandLineInfo *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004f40`
- `0x180004f80`

## callees

- `0x180005040`
- `0x180013330`
- `0x1800d1f9e`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x1800050d1`
- `KERNEL32!CompareStringA` at `0x1800050fe`
- `KERNEL32!CompareStringA` at `0x180005156`
- `KERNEL32!CompareStringA` at `0x180005197`
- `KERNEL32!CompareStringA` at `0x1800050d1`
- `KERNEL32!CompareStringA` at `0x1800050fe`
- `KERNEL32!CompareStringA` at `0x180005156`
- `KERNEL32!CompareStringA` at `0x180005197`

## pseudocode

```c
void __fastcall CCommandLineInfo::ParseParamFlag(CCommandLineInfo *this, const char *a2)
{
  int v4; // r8d
  int v5; // edx

  v4 = *(unsigned __int8 *)a2 - 112;
  if ( *a2 == 112 )
  {
    v4 = *((unsigned __int8 *)a2 + 1) - 116;
    if ( a2[1] == 116 )
      v4 = *((unsigned __int8 *)a2 + 2);
  }
  if ( !v4 )
  {
    *((_DWORD *)this + 5) = 3;
    return;
  }
  v5 = *(unsigned __int8 *)a2 - 112;
  if ( !v5 )
    v5 = *((unsigned __int8 *)a2 + 1);
  if ( !v5 )
  {
    *((_DWORD *)this + 5) = 2;
    return;
  }
  if ( CompareStringA(0x409u, 1u, a2, -1, "Unregister", -1) == 2
    || CompareStringA(0x409u, 1u, a2, -1, "Unregserver", -1) == 2 )
  {
    *((_DWORD *)this + 5) = 5;
  }
  else
  {
    if ( !strcmp_0(a2, "dde") )
    {
      *((_DWORD *)AfxGetModuleState() + 25) = 0;
      *((_DWORD *)this + 5) = 4;
      return;
    }
    if ( CompareStringA(0x409u, 1u, a2, -1, "Embedding", -1) == 2 )
    {
      *((_DWORD *)AfxGetModuleState() + 25) = 0;
      *((_DWORD *)this + 3) = 1;
LABEL_16:
      *((_DWORD *)this + 2) = 0;
      return;
    }
    if ( CompareStringA(0x409u, 1u, a2, -1, "Automation", -1) == 2 )
    {
      *((_DWORD *)AfxGetModuleState() + 25) = 0;
      *((_DWORD *)this + 4) = 1;
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x180005040  push    rbx
0x180005042  push    rbp
0x180005043  push    rdi
0x180005044  push    r14
0x180005046  sub     rsp, 38h
0x18000504a  movzx   r8d, byte ptr [rdx]
0x18000504e  mov     r9d, 70h ; 'p'
0x180005054  mov     rdi, rdx
0x180005057  mov     rbx, rcx
0x18000505a  sub     r8d, r9d
0x18000505d  jnz     short loc_180005077
0x18000505f  movzx   r8d, byte ptr [rdx+1]
0x180005064  sub     r8d, 74h ; 't'
0x180005068  jnz     short loc_180005077
0x18000506a  movzx   r8d, byte ptr [rdx+2]
0x18000506f  xor     eax, eax
0x180005071  movzx   ecx, al
0x180005074  sub     r8d, ecx
0x180005077  test    r8d, r8d
0x18000507a  jnz     short loc_180005088
0x18000507c  mov     dword ptr [rbx+14h], 3
0x180005083  jmp     loc_1800051BA
0x180005088  movzx   edx, byte ptr [rdx]
0x18000508b  sub     edx, r9d
0x18000508e  jnz     short loc_18000509B
0x180005090  movzx   edx, byte ptr [rdi+1]
0x180005094  xor     eax, eax
0x180005096  movzx   ecx, al
0x180005099  sub     edx, ecx
0x18000509b  test    edx, edx
0x18000509d  jnz     short loc_1800050AB
0x18000509f  mov     dword ptr [rbx+14h], 2
0x1800050a6  jmp     loc_1800051BA
0x1800050ab  or      r14d, 0FFFFFFFFh
0x1800050af  lea     rax, String2; "Unregister"
0x1800050b6  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x1800050bb  mov     r9d, r14d; cchCount1
0x1800050be  mov     r8, rdi; lpString1
0x1800050c1  mov     [rsp+58h+lpString2], rax; lpString2
0x1800050c6  mov     ecx, 409h; Locale
0x1800050cb  lea     ebp, [r14+2]
0x1800050cf  mov     edx, ebp; dwCmpFlags
0x1800050d1  call    cs:__imp_CompareStringA
0x1800050d7  cmp     eax, 2
0x1800050da  jz      loc_1800051B3
0x1800050e0  lea     rax, aUnregserver; "Unregserver"
0x1800050e7  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x1800050ec  mov     r9d, r14d; cchCount1
0x1800050ef  mov     [rsp+58h+lpString2], rax; lpString2
0x1800050f4  mov     r8, rdi; lpString1
0x1800050f7  mov     edx, ebp; dwCmpFlags
0x1800050f9  mov     ecx, 409h; Locale
0x1800050fe  call    cs:__imp_CompareStringA
0x180005104  cmp     eax, 2
0x180005107  jz      loc_1800051B3
0x18000510d  lea     rdx, Str2; "dde"
0x180005114  mov     rcx, rdi; Str1
0x180005117  call    strcmp_0
0x18000511c  test    eax, eax
0x18000511e  jnz     short loc_180005138
0x180005120  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180005125  mov     dword ptr [rax+64h], 0
0x18000512c  mov     dword ptr [rbx+14h], 4
0x180005133  jmp     loc_1800051BA
0x180005138  lea     rax, aEmbedding_0; "Embedding"
0x18000513f  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180005144  mov     r9d, r14d; cchCount1
0x180005147  mov     [rsp+58h+lpString2], rax; lpString2
0x18000514c  mov     r8, rdi; lpString1
0x18000514f  mov     edx, ebp; dwCmpFlags
0x180005151  mov     ecx, 409h; Locale
0x180005156  call    cs:__imp_CompareStringA
0x18000515c  cmp     eax, 2
0x18000515f  jnz     short loc_180005179
0x180005161  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180005166  mov     dword ptr [rax+64h], 0
0x18000516d  mov     [rbx+0Ch], ebp
0x180005170  mov     dword ptr [rbx+8], 0
0x180005177  jmp     short loc_1800051BA
0x180005179  lea     rax, aAutomation; "Automation"
0x180005180  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180005185  mov     r9d, r14d; cchCount1
0x180005188  mov     [rsp+58h+lpString2], rax; lpString2
0x18000518d  mov     r8, rdi; lpString1
0x180005190  mov     edx, ebp; dwCmpFlags
0x180005192  mov     ecx, 409h; Locale
0x180005197  call    cs:__imp_CompareStringA
0x18000519d  cmp     eax, 2
0x1800051a0  jnz     short loc_1800051BA
0x1800051a2  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1800051a7  mov     dword ptr [rax+64h], 0
0x1800051ae  mov     [rbx+10h], ebp
0x1800051b1  jmp     short loc_180005170
0x1800051b3  mov     dword ptr [rbx+14h], 5
0x1800051ba  add     rsp, 38h
0x1800051be  pop     r14
0x1800051c0  pop     rdi
0x1800051c1  pop     rbp
0x1800051c2  pop     rbx
0x1800051c3  retn
```
