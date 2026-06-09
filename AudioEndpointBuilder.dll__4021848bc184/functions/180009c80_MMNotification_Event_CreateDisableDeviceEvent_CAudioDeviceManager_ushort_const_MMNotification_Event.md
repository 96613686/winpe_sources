# MMNotification_Event::CreateDisableDeviceEvent(CAudioDeviceManager *,ushort const *,MMNotification_Event * *)

- ea: `0x180009c80`
- end: `0x180009e7c`
- name: `?CreateDisableDeviceEvent@MMNotification_Event@@SAJPEAVCAudioDeviceManager@@PEBGPEAPEAU1@@Z`
- size: `508`
- prototype: `__int64 __fastcall(struct CAudioDeviceManager *, const unsigned __int16 *, struct MMNotification_Event **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d7a0`

## callees

- `0x180009c80`
- `0x18000ab60`
- `0x18003f7a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009cb0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009cb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009d7f`

## pseudocode

```c
__int64 __fastcall MMNotification_Event::CreateDisableDeviceEvent(
        struct CAudioDeviceManager *a1,
        const unsigned __int16 *a2,
        struct MMNotification_Event **a3)
{
  HANDLE ProcessHeap; // rax
  struct MMNotification_Event *v7; // rax
  struct MMNotification_Event *v8; // rsi
  __int64 v10; // r9
  _WORD *v11; // rcx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r14
  _WORD *v14; // rax
  int v15; // ebp
  unsigned __int64 v16; // rdx
  _WORD *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r14
  bool v20; // cf

  *a3 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (struct MMNotification_Event *)HeapAlloc(ProcessHeap, 0, 0x58u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  *((_DWORD *)v7 + 2) = 3;
  *(_QWORD *)v7 = &MMNotification_Event::`vftable';
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 3) = 0;
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 10) = a1;
  if ( a2 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = v12 + 1;
    *((_QWORD *)v7 + 2) = 0;
    if ( v12 + 1 >= v12 && is_mul_ok(v13, 2u) )
    {
      v14 = CoTaskMemAlloc(2 * v13);
      *((_QWORD *)v8 + 2) = v14;
      if ( v14 )
        v15 = 0;
      else
        v15 = -2147024882;
      if ( v15 >= 0 )
      {
        if ( (v14 || v12 == -1) && v13 <= 0x7FFFFFFF )
        {
          if ( v12 >= 0x7FFFFFFF )
          {
            if ( v12 != -1 )
              *v14 = 0;
          }
          else
          {
            v16 = v12 + 1;
            v17 = v14;
            v18 = 0;
            do
            {
              if ( !v12 )
                break;
              if ( !*a2 )
                break;
              *v17++ = *a2++;
              --v12;
              ++v18;
              --v16;
            }
            while ( v16 );
            v10 = v18 - 1;
            if ( v16 )
              v10 = v18;
            v11 = v17 - 1;
            if ( v16 )
              v11 = v17;
            *v11 = 0;
            if ( v16 )
            {
              v20 = v13 == v10;
              v19 = v13 - v10;
              if ( !v20 && v19 != 1 && (unsigned __int64)(2 * v19) > 2 )
                memset_0(&v14[v10 + 1], 0, 2 * v19 - 2);
            }
          }
        }
        else
        {
          *v14 = 0;
        }
      }
    }
    else
    {
      v15 = -2147024362;
    }
  }
  else
  {
    v15 = 0;
  }
  if ( v15 >= 0 )
    *a3 = v8;
  else
    MMNotification_Event::`scalar deleting destructor'(v8, 1u);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180009c80  mov     [rsp+arg_8], rbx
0x180009c85  push    rbp
0x180009c86  push    rsi
0x180009c87  push    rdi
0x180009c88  push    r12
0x180009c8a  push    r15
0x180009c8c  sub     rsp, 20h
0x180009c90  xor     r12d, r12d
0x180009c93  mov     r15, r8
0x180009c96  mov     [r8], r12
0x180009c99  mov     rdi, rdx
0x180009c9c  mov     rbx, rcx
0x180009c9f  call    cs:__imp_GetProcessHeap
0x180009ca5  xor     edx, edx; dwFlags
0x180009ca7  mov     r8d, 58h ; 'X'; dwBytes
0x180009cad  mov     rcx, rax; hHeap
0x180009cb0  call    cs:__imp_HeapAlloc
0x180009cb6  mov     [rsp+48h+arg_10], rax
0x180009cbb  mov     rsi, rax
0x180009cbe  test    rax, rax
0x180009cc1  jnz     short loc_180009D14
0x180009cc3  mov     eax, 8007000Eh
0x180009cc8  jmp     short loc_180009D03
0x180009cca  lea     r9, [rcx-1]
0x180009cce  test    rdx, rdx
0x180009cd1  cmovnz  r9, rcx
0x180009cd5  lea     rcx, [r8-2]
0x180009cd9  cmovnz  rcx, r8
0x180009cdd  mov     [rcx], r12w
0x180009ce1  jnz     loc_180009E14
0x180009ce7  mov     r14, [rsp+48h+arg_0]
0x180009cec  test    ebp, ebp
0x180009cee  jns     loc_180009E72
0x180009cf4  mov     edx, 1; unsigned int
0x180009cf9  mov     rcx, rsi; this
0x180009cfc  call    ??_GMMNotification_Event@@UEAAPEAXI@Z; MMNotification_Event::`scalar deleting destructor'(uint)
0x180009d01  mov     eax, ebp
0x180009d03  mov     rbx, [rsp+48h+arg_8]
0x180009d08  add     rsp, 20h
0x180009d0c  pop     r15
0x180009d0e  pop     r12
0x180009d10  pop     rdi
0x180009d11  pop     rsi
0x180009d12  pop     rbp
0x180009d13  retn
0x180009d14  mov     dword ptr [rsi+8], 3
0x180009d1b  lea     rax, ??_7MMNotification_Event@@6B@; const MMNotification_Event::`vftable'
0x180009d22  mov     [rsi], rax
0x180009d25  mov     [rsi+10h], r12
0x180009d29  mov     [rsi+18h], r12
0x180009d2d  mov     [rsi+30h], r12
0x180009d31  mov     [rsi+50h], rbx
0x180009d35  test    rsi, rsi
0x180009d38  jz      short loc_180009CC3
0x180009d3a  test    rdi, rdi
0x180009d3d  jz      loc_180009E6A
0x180009d43  mov     [rsp+48h+arg_0], r14
0x180009d48  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180009d4f  nop
0x180009d50  inc     rbx
0x180009d53  cmp     [rdi+rbx*2], r12w
0x180009d58  jnz     short loc_180009D50
0x180009d5a  lea     r14, [rbx+1]
0x180009d5e  mov     [rsi+10h], r12
0x180009d62  cmp     r14, rbx
0x180009d65  jb      loc_180009E05
0x180009d6b  mov     eax, 2
0x180009d70  mul     r14
0x180009d73  test    rdx, rdx
0x180009d76  jnz     loc_180009E05
0x180009d7c  mov     rcx, rax; cb
0x180009d7f  call    cs:__imp_CoTaskMemAlloc
0x180009d85  mov     [rsi+10h], rax
0x180009d89  mov     r10, rax
0x180009d8c  test    rax, rax
0x180009d8f  jnz     short loc_180009E0F
0x180009d91  mov     ebp, 8007000Eh
0x180009d96  test    ebp, ebp
0x180009d98  js      loc_180009CE7
0x180009d9e  test    r10, r10
0x180009da1  jz      loc_180009E46
0x180009da7  cmp     r14, 7FFFFFFFh
0x180009dae  ja      loc_180009E4F
0x180009db4  cmp     rbx, 7FFFFFFFh
0x180009dbb  jnb     loc_180009E58
0x180009dc1  test    r14, r14
0x180009dc4  jz      loc_180009CE7
0x180009dca  mov     rdx, r14
0x180009dcd  mov     r8, r10
0x180009dd0  mov     rcx, r12
0x180009dd3  test    rbx, rbx
0x180009dd6  jz      loc_180009CCA
0x180009ddc  movzx   eax, word ptr [rdi]
0x180009ddf  test    ax, ax
0x180009de2  jz      loc_180009CCA
0x180009de8  mov     [r8], ax
0x180009dec  add     rdi, 2
0x180009df0  add     r8, 2
0x180009df4  dec     rbx
0x180009df7  inc     rcx
0x180009dfa  sub     rdx, 1
0x180009dfe  jnz     short loc_180009DD3
0x180009e00  jmp     loc_180009CCA
0x180009e05  mov     ebp, 80070216h
0x180009e0a  jmp     loc_180009CE7
0x180009e0f  mov     ebp, r12d
0x180009e12  jmp     short loc_180009D96
0x180009e14  sub     r14, r9
0x180009e17  cmp     r14, 1
0x180009e1b  jbe     loc_180009CE7
0x180009e21  lea     r8, [r14+r14]
0x180009e25  cmp     r8, 2
0x180009e29  jbe     loc_180009CE7
0x180009e2f  inc     r9
0x180009e32  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180009e36  xor     edx, edx; Val
0x180009e38  lea     rcx, [r10+r9*2]; void *
0x180009e3c  call    memset_0
0x180009e41  jmp     loc_180009CE7
0x180009e46  test    r14, r14
0x180009e49  jz      loc_180009DA7
0x180009e4f  mov     [rax], r12w
0x180009e53  jmp     loc_180009CE7
0x180009e58  test    r14, r14
0x180009e5b  jz      loc_180009CE7
0x180009e61  mov     [rax], r12w
0x180009e65  jmp     loc_180009CE7
0x180009e6a  mov     ebp, r12d
0x180009e6d  jmp     loc_180009CEC
0x180009e72  mov     [r15], rsi
0x180009e75  mov     eax, ebp
0x180009e77  jmp     loc_180009D03
```
