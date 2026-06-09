# CPimcTablet::GetCursorButtonInfo(int,int,ushort * *,_GUID *)

- ea: `0x180009910`
- end: `0x180009add`
- name: `?GetCursorButtonInfo@CPimcTablet@@UEAAJHHPEAPEAGPEAU_GUID@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(CPimcTablet *__hidden this, int, int, unsigned __int16 **, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009910`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180009a3d`
- `ole32!CoTaskMemAlloc` at `0x180009a3d`

## pseudocode

```c
__int64 __fastcall CPimcTablet::GetCursorButtonInfo(
        CPimcTablet *this,
        int a2,
        int a3,
        unsigned __int16 **a4,
        struct _GUID *a5)
{
  unsigned int v6; // r10d
  __int64 v7; // rdx
  __int64 v8; // r15
  char *v9; // rdi
  char *v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  unsigned __int16 *v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rdx
  signed __int64 v18; // rdi
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // rax

  v6 = (a2 >> 31) & 0x80070057;
  if ( a2 >> 31 != -1 )
  {
    v6 = (unsigned int)a2 >= *((_DWORD *)this + 13) ? 0x80070057 : 0;
    if ( (unsigned int)a2 < *((_DWORD *)this + 13) )
    {
      v6 = (a3 >> 31) & 0x80070057;
      if ( a3 >> 31 != -1 )
      {
        v6 = -2147024809;
        v7 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * a2);
        if ( a3 < *(_DWORD *)(v7 + 16) )
        {
          v6 = a4 == 0 ? 0x80070057 : 0;
          if ( a4 )
          {
            v6 = a5 == 0 ? 0x80070057 : 0;
            if ( a5 )
            {
              v8 = *(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL * a3);
              v9 = *(char **)v8;
              if ( *(_QWORD *)v8 )
              {
                v10 = *(char **)v8;
                v11 = 0x7FFFFFFF;
                do
                {
                  if ( !*(_WORD *)v10 )
                    break;
                  v10 += 2;
                  --v11;
                }
                while ( v11 );
                v6 = v11 == 0 ? 0x80070057 : 0;
                v12 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
                if ( v11 )
                {
                  v13 = v12 + 1;
                  if ( v12 + 1 >= v12 && (v14 = 2 * v13, is_mul_ok(v13, 2u)) )
                  {
                    v15 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13);
                    *a4 = v15;
                    v6 = v15 == 0 ? 0x8007000E : 0;
                    if ( v15 )
                    {
                      v16 = v14 >> 1;
                      if ( v16 )
                      {
                        if ( v16 <= 0x7FFFFFFF )
                        {
                          v17 = 2147483646 - v16;
                          v18 = v9 - (char *)v15;
                          do
                          {
                            if ( !(v17 + v16) )
                              break;
                            v19 = *(unsigned __int16 *)((char *)v15 + v18);
                            if ( !v19 )
                              break;
                            *v15++ = v19;
                            --v16;
                          }
                          while ( v16 );
                          v20 = v15 - 1;
                          if ( v16 )
                            v20 = v15;
                          *v20 = 0;
                        }
                        else
                        {
                          *v15 = 0;
                        }
                      }
                      *a5 = *(struct _GUID *)(v8 + 8);
                    }
                  }
                  else
                  {
                    return (unsigned int)-2147024362;
                  }
                }
              }
              else
              {
                return (unsigned int)-2147024809;
              }
            }
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180009910  mov     rax, rsp
0x180009913  mov     [rax+8], rbx
0x180009917  mov     [rax+10h], rbp
0x18000991b  mov     [rax+18h], rsi
0x18000991f  mov     [rax+20h], rdi
0x180009923  push    r12
0x180009925  push    r14
0x180009927  push    r15
0x180009929  sub     rsp, 20h
0x18000992d  mov     r10d, edx
0x180009930  mov     r14, r9
0x180009933  sar     r10d, 1Fh
0x180009937  mov     r9d, 80070057h
0x18000993d  mov     rax, rcx
0x180009940  and     r10d, r9d
0x180009943  jl      loc_180009ABB
0x180009949  cmp     edx, [rcx+34h]
0x18000994c  sbb     r10d, r10d
0x18000994f  not     r10d
0x180009952  and     r10d, r9d
0x180009955  cmp     edx, [rcx+34h]
0x180009958  jnb     loc_180009ABB
0x18000995e  mov     r10d, r8d
0x180009961  sar     r10d, 1Fh
0x180009965  and     r10d, r9d
0x180009968  jl      loc_180009ABB
0x18000996e  mov     rax, [rax+38h]
0x180009972  xor     ebp, ebp
0x180009974  movsxd  rcx, edx
0x180009977  mov     r10d, r9d
0x18000997a  mov     rdx, [rax+rcx*8]
0x18000997e  cmp     r8d, [rdx+10h]
0x180009982  cmovl   r10d, ebp
0x180009986  jge     loc_180009ABB
0x18000998c  mov     rax, r14
0x18000998f  neg     rax
0x180009992  sbb     r10d, r10d
0x180009995  not     r10d
0x180009998  and     r10d, r9d
0x18000999b  test    r14, r14
0x18000999e  jz      loc_180009ABB
0x1800099a4  mov     rsi, [rsp+38h+arg_20]
0x1800099a9  mov     rax, rsi
0x1800099ac  neg     rax
0x1800099af  sbb     r10d, r10d
0x1800099b2  not     r10d
0x1800099b5  and     r10d, r9d
0x1800099b8  test    rsi, rsi
0x1800099bb  jz      loc_180009ABB
0x1800099c1  mov     rax, [rdx+18h]
0x1800099c5  movsxd  rcx, r8d
0x1800099c8  mov     r15, [rax+rcx*8]
0x1800099cc  mov     rdi, [r15]
0x1800099cf  test    rdi, rdi
0x1800099d2  jz      loc_180009AB8
0x1800099d8  mov     r12d, 7FFFFFFFh
0x1800099de  mov     rax, rdi
0x1800099e1  mov     edx, r12d
0x1800099e4  cmp     [rax], bp
0x1800099e7  jz      short loc_1800099F3
0x1800099e9  add     rax, 2
0x1800099ed  sub     rdx, 1
0x1800099f1  jnz     short loc_1800099E4
0x1800099f3  mov     rax, rdx
0x1800099f6  mov     rcx, r12
0x1800099f9  neg     rax
0x1800099fc  mov     rax, rdx
0x1800099ff  sbb     r10d, r10d
0x180009a02  sub     rcx, rdx
0x180009a05  not     r10d
0x180009a08  and     r10d, r9d
0x180009a0b  neg     rax
0x180009a0e  sbb     r8, r8
0x180009a11  and     r8, rcx
0x180009a14  test    rdx, rdx
0x180009a17  jz      loc_180009ABB
0x180009a1d  lea     rcx, [r8+1]
0x180009a21  cmp     rcx, r8
0x180009a24  jb      loc_180009AB0
0x180009a2a  mov     eax, 2
0x180009a2f  mul     rcx
0x180009a32  mov     rbx, rax
0x180009a35  test    rdx, rdx
0x180009a38  jnz     short loc_180009AB0
0x180009a3a  mov     rcx, rax; cb
0x180009a3d  call    cs:__imp_CoTaskMemAlloc
0x180009a43  mov     rcx, rax
0x180009a46  mov     [r14], rax
0x180009a49  neg     rax
0x180009a4c  sbb     r10d, r10d
0x180009a4f  not     r10d
0x180009a52  and     r10d, 8007000Eh
0x180009a59  test    rcx, rcx
0x180009a5c  jz      short loc_180009ABB
0x180009a5e  shr     rbx, 1
0x180009a61  jz      short loc_180009AA5
0x180009a63  cmp     rbx, r12
0x180009a66  jbe     short loc_180009A6D
0x180009a68  mov     [rcx], bp
0x180009a6b  jmp     short loc_180009AA5
0x180009a6d  mov     edx, 7FFFFFFEh
0x180009a72  sub     rdx, rbx
0x180009a75  sub     rdi, rcx
0x180009a78  lea     rax, [rdx+rbx]
0x180009a7c  test    rax, rax
0x180009a7f  jz      short loc_180009A97
0x180009a81  movzx   eax, word ptr [rdi+rcx]
0x180009a85  test    ax, ax
0x180009a88  jz      short loc_180009A97
0x180009a8a  mov     [rcx], ax
0x180009a8d  add     rcx, 2
0x180009a91  sub     rbx, 1
0x180009a95  jnz     short loc_180009A78
0x180009a97  test    rbx, rbx
0x180009a9a  lea     rax, [rcx-2]
0x180009a9e  cmovnz  rax, rcx
0x180009aa2  mov     [rax], bp
0x180009aa5  movups  xmm0, xmmword ptr [r15+8]
0x180009aaa  movdqu  xmmword ptr [rsi], xmm0
0x180009aae  jmp     short loc_180009ABB
0x180009ab0  mov     r10d, 80070216h
0x180009ab6  jmp     short loc_180009ABB
0x180009ab8  mov     r10d, r9d
0x180009abb  mov     rbx, [rsp+38h+arg_0]
0x180009ac0  mov     eax, r10d
0x180009ac3  mov     rbp, [rsp+38h+arg_8]
0x180009ac8  mov     rsi, [rsp+38h+arg_10]
0x180009acd  mov     rdi, [rsp+38h+arg_18]
0x180009ad2  add     rsp, 20h
0x180009ad6  pop     r15
0x180009ad8  pop     r14
0x180009ada  pop     r12
0x180009adc  retn
```
