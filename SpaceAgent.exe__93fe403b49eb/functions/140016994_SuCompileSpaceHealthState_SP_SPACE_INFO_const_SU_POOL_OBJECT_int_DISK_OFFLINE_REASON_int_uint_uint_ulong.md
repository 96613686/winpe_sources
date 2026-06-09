# SuCompileSpaceHealthState(_SP_SPACE_INFO const *,_SU_POOL_OBJECT *,int,_DISK_OFFLINE_REASON,int,uint *,uint *,ulong *)

- ea: `0x140016994`
- end: `0x140016bbe`
- name: `?SuCompileSpaceHealthState@@YAXPEBU_SP_SPACE_INFO@@PEAU_SU_POOL_OBJECT@@HW4_DISK_OFFLINE_REASON@@HPEAI3PEAK@Z`
- size: `554`
- prototype: `void __fastcall(_DWORD *, __int64, int, int, __int64, _DWORD *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014988`

## callees

- `0x1400162a8`
- `0x140016994`

## pseudocode

```c
void __fastcall SuCompileSpaceHealthState(
        _DWORD *a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        _DWORD *a6,
        int *a7,
        int *a8)
{
  int v9; // r11d
  int v11; // r10d
  int v12; // eax
  int v13; // eax
  int v14; // r14d
  int v15; // esi
  int v16; // esi
  int v17; // eax
  int v18; // ebp
  int v19; // ebp
  int v20; // ebp

  v9 = a1[653];
  v11 = a1[654];
  *a7 = 33034;
  switch ( v9 )
  {
    case 1:
      *a6 = 1;
      break;
    case 2:
      *a6 = 2;
      break;
    case 3:
      *a6 = 3;
      break;
    default:
      *a6 = 0;
      break;
  }
  if ( v11 != 7 )
  {
    if ( v11 != 1 )
    {
      switch ( v11 )
      {
        case 2:
          *a7 = 33047;
          break;
        case 3:
          *a7 = 33024;
          break;
        case 4:
          *a7 = 33025;
          break;
        case 5:
          *a7 = 33026;
          *a6 = 3;
          break;
      }
      goto LABEL_27;
    }
    v12 = a1[665];
    if ( v12 == 3 )
    {
      *a7 = 33027;
    }
    else
    {
      if ( v12 != 4 )
      {
        if ( v12 == 2 )
        {
          *a7 = 33029;
        }
        else if ( v12 == 5 )
        {
          *a7 = 33030;
        }
        goto LABEL_27;
      }
      *a7 = 33028;
    }
    *a6 = 1;
  }
LABEL_27:
  if ( v9 != 3 && (v9 != 2 || v11 != 5) )
    goto LABEL_41;
  v13 = a1[674];
  if ( v13 == 2 )
  {
    *a6 = 3;
LABEL_42:
    if ( a3 == 1 )
    {
      v18 = a4 - 1;
      if ( v18 )
      {
        v19 = v18 - 4;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            if ( v20 == 1 )
            {
              *a6 = 1;
              *a7 = 33046;
            }
            else
            {
              *a7 = 33040;
            }
          }
          else
          {
            *a6 = 1;
            *a7 = 33045;
          }
        }
        else
        {
          *a6 = 1;
          *a7 = 33042;
        }
      }
      else
      {
        *a7 = 33041;
      }
    }
    return;
  }
  if ( v13 != 1 )
  {
LABEL_41:
    if ( *a6 != 3 )
      return;
    goto LABEL_42;
  }
  v14 = a1[691];
  v15 = a1[689];
  if ( !(unsigned int)SuNumberOfDrivesByUsage(a2, a2, a1) )
  {
    *a6 = 0;
    return;
  }
  v16 = v14 * v15;
  if ( !v16 )
  {
    *a6 = 3;
    goto LABEL_41;
  }
  v17 = 33031;
  *a6 = 1;
  if ( v16 != 1 )
    v17 = 33043;
  *a7 = v17;
  *a8 = v16;
}

```

## disassembly

```asm
0x140016994  push    rbx
0x140016996  push    rbp
0x140016997  push    rsi
0x140016998  push    rdi
0x140016999  push    r12
0x14001699b  push    r13
0x14001699d  push    r14
0x14001699f  push    r15
0x1400169a1  sub     rsp, 38h
0x1400169a5  mov     rdi, [rsp+78h+arg_30]
0x1400169ad  mov     ebp, r9d
0x1400169b0  mov     r11d, [rcx+0A34h]
0x1400169b7  mov     r15d, r8d
0x1400169ba  mov     r10d, [rcx+0A38h]
0x1400169c1  mov     r8d, 2
0x1400169c7  mov     rbx, [rsp+78h+arg_28]
0x1400169cf  mov     r9d, r11d
0x1400169d2  mov     dword ptr [rdi], 810Ah
0x1400169d8  lea     r12d, [r8-1]
0x1400169dc  lea     r13d, [r8+1]
0x1400169e0  sub     r9d, r12d
0x1400169e3  jz      short loc_140016A01
0x1400169e5  sub     r9d, r12d
0x1400169e8  jz      short loc_1400169FC
0x1400169ea  cmp     r9d, r12d
0x1400169ed  jz      short loc_1400169F7
0x1400169ef  mov     dword ptr [rbx], 0
0x1400169f5  jmp     short loc_140016A04
0x1400169f7  mov     [rbx], r13d
0x1400169fa  jmp     short loc_140016A04
0x1400169fc  mov     [rbx], r8d
0x1400169ff  jmp     short loc_140016A04
0x140016a01  mov     [rbx], r12d
0x140016a04  cmp     r10d, 7
0x140016a08  jz      short loc_140016A83
0x140016a0a  cmp     r10d, r12d
0x140016a0d  jnz     short loc_140016A4C
0x140016a0f  mov     eax, [rcx+0A64h]
0x140016a15  cmp     eax, r13d
0x140016a18  jnz     short loc_140016A22
0x140016a1a  mov     dword ptr [rdi], 8103h
0x140016a20  jmp     short loc_140016A2D
0x140016a22  cmp     eax, 4
0x140016a25  jnz     short loc_140016A32
0x140016a27  mov     dword ptr [rdi], 8104h
0x140016a2d  mov     [rbx], r12d
0x140016a30  jmp     short loc_140016A83
0x140016a32  cmp     eax, r8d
0x140016a35  jnz     short loc_140016A3F
0x140016a37  mov     dword ptr [rdi], 8105h
0x140016a3d  jmp     short loc_140016A83
0x140016a3f  cmp     eax, 5
0x140016a42  jnz     short loc_140016A83
0x140016a44  mov     dword ptr [rdi], 8106h
0x140016a4a  jmp     short loc_140016A83
0x140016a4c  cmp     r10d, r8d
0x140016a4f  jnz     short loc_140016A59
0x140016a51  mov     dword ptr [rdi], 8117h
0x140016a57  jmp     short loc_140016A83
0x140016a59  cmp     r10d, r13d
0x140016a5c  jnz     short loc_140016A66
0x140016a5e  mov     dword ptr [rdi], 8100h
0x140016a64  jmp     short loc_140016A83
0x140016a66  cmp     r10d, 4
0x140016a6a  jnz     short loc_140016A74
0x140016a6c  mov     dword ptr [rdi], 8101h
0x140016a72  jmp     short loc_140016A83
0x140016a74  cmp     r10d, 5
0x140016a78  jnz     short loc_140016A83
0x140016a7a  mov     dword ptr [rdi], 8102h
0x140016a80  mov     [rbx], r13d
0x140016a83  cmp     r11d, r13d
0x140016a86  jz      short loc_140016A9B
0x140016a88  cmp     r11d, r8d
0x140016a8b  jnz     loc_140016B60
0x140016a91  cmp     r10d, 5
0x140016a95  jnz     loc_140016B60
0x140016a9b  mov     eax, [rcx+0A88h]
0x140016aa1  cmp     eax, r8d
0x140016aa4  jnz     short loc_140016AAE
0x140016aa6  mov     [rbx], r13d
0x140016aa9  jmp     loc_140016B65
0x140016aae  cmp     eax, r12d
0x140016ab1  jnz     loc_140016B60
0x140016ab7  mov     r14d, [rcx+0ACCh]
0x140016abe  lea     rax, [rsp+78h+arg_20]
0x140016ac6  mov     esi, [rcx+0AC4h]
0x140016acc  mov     r8, rcx
0x140016acf  mov     [rsp+78h+var_50], rax
0x140016ad4  mov     rcx, rdx
0x140016ad7  lea     rax, [rsp+78h+arg_28]
0x140016adf  mov     [rsp+78h+arg_20], 0
0x140016aea  mov     [rsp+78h+var_58], rax
0x140016aef  mov     dword ptr [rsp+78h+arg_28], 0
0x140016afa  call    ?SuNumberOfDrivesByUsage@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_DRIVE_USAGE@@PEBU_SP_SPACE_INFO@@HPEAI3@Z; SuNumberOfDrivesByUsage(_SU_POOL_OBJECT *,_SP_DRIVE_USAGE,_SP_SPACE_INFO const *,int,uint *,uint *)
0x140016aff  test    eax, eax
0x140016b01  jnz     short loc_140016B0A
0x140016b03  mov     [rbx], eax
0x140016b05  jmp     loc_140016BAD
0x140016b0a  imul    esi, r14d
0x140016b0e  cmp     [rsp+78h+arg_20], esi
0x140016b15  jnb     short loc_140016B2B
0x140016b17  sub     esi, [rsp+78h+arg_20]
0x140016b1e  mov     eax, 8107h
0x140016b23  mov     [rbx], r12d
0x140016b26  lea     ecx, [rax+0Ch]
0x140016b29  jmp     short loc_140016B49
0x140016b2b  cmp     dword ptr [rsp+78h+arg_28], esi
0x140016b32  jnb     short loc_140016B5D
0x140016b34  sub     esi, dword ptr [rsp+78h+arg_28]
0x140016b3b  mov     eax, 8108h
0x140016b40  mov     dword ptr [rbx], 2
0x140016b46  lea     ecx, [rax+0Ch]
0x140016b49  cmp     esi, r12d
0x140016b4c  cmovnz  eax, ecx
0x140016b4f  mov     [rdi], eax
0x140016b51  mov     rax, [rsp+78h+arg_38]
0x140016b59  mov     [rax], esi
0x140016b5b  jmp     short loc_140016BAD
0x140016b5d  mov     [rbx], r13d
0x140016b60  cmp     [rbx], r13d
0x140016b63  jnz     short loc_140016BAD
0x140016b65  cmp     r15d, r12d
0x140016b68  jnz     short loc_140016BAD
0x140016b6a  sub     ebp, r12d
0x140016b6d  jz      short loc_140016BA7
0x140016b6f  sub     ebp, 4
0x140016b72  jz      short loc_140016B9C
0x140016b74  sub     ebp, r12d
0x140016b77  jz      short loc_140016B91
0x140016b79  cmp     ebp, r12d
0x140016b7c  jz      short loc_140016B86
0x140016b7e  mov     dword ptr [rdi], 8110h
0x140016b84  jmp     short loc_140016BAD
0x140016b86  mov     [rbx], r12d
0x140016b89  mov     dword ptr [rdi], 8116h
0x140016b8f  jmp     short loc_140016BAD
0x140016b91  mov     [rbx], r12d
0x140016b94  mov     dword ptr [rdi], 8115h
0x140016b9a  jmp     short loc_140016BAD
0x140016b9c  mov     [rbx], r12d
0x140016b9f  mov     dword ptr [rdi], 8112h
0x140016ba5  jmp     short loc_140016BAD
0x140016ba7  mov     dword ptr [rdi], 8111h
0x140016bad  add     rsp, 38h
0x140016bb1  pop     r15
0x140016bb3  pop     r14
0x140016bb5  pop     r13
0x140016bb7  pop     r12
0x140016bb9  pop     rdi
0x140016bba  pop     rsi
0x140016bbb  pop     rbp
0x140016bbc  pop     rbx
0x140016bbd  retn
```
