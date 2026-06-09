# CSyncServices::CreateRecoverableErrorData(IRecoverableErrorData * *)

- ea: `0x18002c3c0`
- end: `0x18002c4ef`
- name: `?CreateRecoverableErrorData@CSyncServices@@UEAAJPEAPEAUIRecoverableErrorData@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, struct IRecoverableErrorData **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18002c500`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002c3c0`

## string_xrefs

- `0x18002c3f6`: `CSyncServices::CreateRecoverableErrorData`
- `0x18002c4c0`: `CSyncServices::CreateRecoverableErrorData`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateRecoverableErrorData(CSyncServices *this, struct IRecoverableErrorData **a2)
{
  PVOID *v3; // rcx
  unsigned int v4; // ebx
  struct IRecoverableErrorData *v5; // rbx

  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateRecoverableErrorData");
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = -2147467261;
  if ( a2 )
  {
    v5 = (struct IRecoverableErrorData *)SeAlloc(0x20u);
    if ( v5 )
    {
      v5[2].lpVtbl = 0;
      v5->lpVtbl = (struct IRecoverableErrorDataVtbl *)&CRecoverableErrorData::`vftable';
      LODWORD(v5[1].lpVtbl) = 1;
      v5[3].lpVtbl = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_dfd73d025457336d0f1493a3680bf7bb_Traceguids,
          "CRecoverableErrorData::CRecoverableErrorData");
      }
      _InterlockedIncrement(&g_cRefThisDll);
      *a2 = v5;
      v4 = 0;
    }
    else
    {
      v4 = -2147024882;
      *a2 = 0;
    }
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 && *((_BYTE *)v3 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v3[2],
      47,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateRecoverableErrorData",
      v4);
  return v4;
}

```

## disassembly

```asm
0x18002c3c0  mov     [rsp+arg_0], rbx
0x18002c3c5  mov     [rsp+arg_8], rdi
0x18002c3ca  push    r14
0x18002c3cc  sub     rsp, 30h
0x18002c3d0  mov     rdi, rdx
0x18002c3d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3da  lea     r14, WPP_GLOBAL_Control
0x18002c3e1  cmp     rcx, r14
0x18002c3e4  jz      short loc_18002C415
0x18002c3e6  test    byte ptr [rcx+1Ch], 2
0x18002c3ea  jz      short loc_18002C415
0x18002c3ec  cmp     byte ptr [rcx+19h], 5
0x18002c3f0  jb      short loc_18002C415
0x18002c3f2  mov     rcx, [rcx+10h]
0x18002c3f6  lea     r9, aCsyncservicesC_12; "CSyncServices::CreateRecoverableErrorDa"...
0x18002c3fd  mov     edx, 2Eh ; '.'
0x18002c402  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c409  call    WPP_SF_s
0x18002c40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c415  mov     ebx, 80004003h
0x18002c41a  test    rdi, rdi
0x18002c41d  jz      loc_18002C4AB
0x18002c423  mov     ecx, 20h ; ' '; unsigned __int64
0x18002c428  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002c42d  mov     rbx, rax
0x18002c430  test    rax, rax
0x18002c433  jz      short loc_18002C498
0x18002c435  lea     rax, ??_7CRecoverableErrorData@@6B@; const CRecoverableErrorData::`vftable'
0x18002c43c  mov     qword ptr [rbx+10h], 0
0x18002c444  mov     [rbx], rax
0x18002c447  mov     dword ptr [rbx+8], 1
0x18002c44e  mov     qword ptr [rbx+18h], 0
0x18002c456  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c45d  cmp     rcx, r14
0x18002c460  jz      short loc_18002C48A
0x18002c462  test    byte ptr [rcx+1Ch], 8
0x18002c466  jz      short loc_18002C48A
0x18002c468  cmp     byte ptr [rcx+19h], 5
0x18002c46c  jb      short loc_18002C48A
0x18002c46e  mov     rcx, [rcx+10h]
0x18002c472  lea     r9, aCrecoverableer_12; "CRecoverableErrorData::CRecoverableErro"...
0x18002c479  mov     edx, 1Ch
0x18002c47e  lea     r8, WPP_dfd73d025457336d0f1493a3680bf7bb_Traceguids
0x18002c485  call    WPP_SF_s
0x18002c48a  lock inc cs:?g_cRefThisDll@@3JC; long volatile g_cRefThisDll
0x18002c491  mov     [rdi], rbx
0x18002c494  xor     ebx, ebx
0x18002c496  jmp     short loc_18002C4A4
0x18002c498  mov     ebx, 8007000Eh
0x18002c49d  mov     qword ptr [rdi], 0
0x18002c4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4ab  cmp     rcx, r14
0x18002c4ae  jz      short loc_18002C4DC
0x18002c4b0  test    byte ptr [rcx+1Ch], 2
0x18002c4b4  jz      short loc_18002C4DC
0x18002c4b6  cmp     byte ptr [rcx+19h], 5
0x18002c4ba  jb      short loc_18002C4DC
0x18002c4bc  mov     rcx, [rcx+10h]
0x18002c4c0  lea     r9, aCsyncservicesC_12; "CSyncServices::CreateRecoverableErrorDa"...
0x18002c4c7  mov     edx, 2Fh ; '/'
0x18002c4cc  mov     [rsp+38h+var_18], ebx
0x18002c4d0  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c4d7  call    WPP_SF_sD
0x18002c4dc  mov     rdi, [rsp+38h+arg_8]
0x18002c4e1  mov     eax, ebx
0x18002c4e3  mov     rbx, [rsp+38h+arg_0]
0x18002c4e8  add     rsp, 30h
0x18002c4ec  pop     r14
0x18002c4ee  retn
```
