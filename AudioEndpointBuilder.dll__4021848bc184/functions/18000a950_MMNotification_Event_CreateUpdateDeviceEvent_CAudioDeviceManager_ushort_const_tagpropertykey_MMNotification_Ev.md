# MMNotification_Event::CreateUpdateDeviceEvent(CAudioDeviceManager *,ushort const *,_tagpropertykey,MMNotification_Event * *)

- ea: `0x18000a950`
- end: `0x18000ab50`
- name: `?CreateUpdateDeviceEvent@MMNotification_Event@@SAJPEAVCAudioDeviceManager@@PEBGU_tagpropertykey@@PEAPEAU1@@Z`
- size: `512`
- prototype: `__int64 __fastcall(struct CAudioDeviceManager *, const unsigned __int16 *, struct _tagpropertykey *__struct_ptr, struct MMNotification_Event **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003da60`

## callees

- `0x18000a950`
- `0x18000ab60`
- `0x18003f7a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a989`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a989`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a978`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa0f`

## pseudocode

```c
__int64 __fastcall MMNotification_Event::CreateUpdateDeviceEvent(
        struct CAudioDeviceManager *a1,
        const unsigned __int16 *a2,
        struct _tagpropertykey *a3,
        struct MMNotification_Event **a4)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rax
  _DWORD *v10; // rsi
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // r14
  _WORD *v13; // rax
  int v14; // ebp
  unsigned __int64 v15; // rdx
  _WORD *v16; // r8
  __int64 v17; // rcx
  __int64 v18; // r9
  _WORD *v19; // rcx
  __int64 result; // rax
  DWORD pid; // eax
  __int64 v22; // r14
  bool v23; // cf

  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0x58u);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  v9[2] = 5;
  *(_QWORD *)v9 = &MMNotification_Event::`vftable';
  *((_QWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 3) = 0;
  *((_QWORD *)v9 + 6) = 0;
  *((_QWORD *)v9 + 10) = a1;
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v12 = v11 + 1;
    *((_QWORD *)v9 + 2) = 0;
    if ( v11 + 1 >= v11 && is_mul_ok(v12, 2u) )
    {
      v13 = CoTaskMemAlloc(2 * v12);
      *((_QWORD *)v10 + 2) = v13;
      if ( v13 )
        v14 = 0;
      else
        v14 = -2147024882;
      if ( v14 >= 0 )
      {
        if ( (v13 || v11 == -1) && v12 <= 0x7FFFFFFF )
        {
          if ( v11 >= 0x7FFFFFFF )
          {
            if ( v11 != -1 )
              *v13 = 0;
          }
          else
          {
            v15 = v11 + 1;
            v16 = v13;
            v17 = 0;
            do
            {
              if ( !v11 )
                break;
              if ( !*a2 )
                break;
              *v16++ = *a2++;
              --v11;
              ++v17;
              --v15;
            }
            while ( v15 );
            v18 = v17 - 1;
            if ( v15 )
              v18 = v17;
            v19 = v16 - 1;
            if ( v15 )
              v19 = v16;
            *v19 = 0;
            if ( v15 )
            {
              v23 = v12 == v18;
              v22 = v12 - v18;
              if ( !v23 && v22 != 1 && (unsigned __int64)(2 * v22) > 2 )
                memset_0(&v13[v18 + 1], 0, 2 * v22 - 2);
            }
          }
        }
        else
        {
          *v13 = 0;
        }
      }
    }
    else
    {
      v14 = -2147024362;
    }
  }
  else
  {
    v14 = 0;
  }
  if ( v14 >= 0 )
  {
    pid = a3->pid;
    *(GUID *)(v10 + 14) = a3->fmtid;
    v10[18] = pid;
    result = (unsigned int)v14;
    *a4 = (struct MMNotification_Event *)v10;
  }
  else
  {
    MMNotification_Event::`scalar deleting destructor'((MMNotification_Event *)v10, 1u);
    return (unsigned int)v14;
  }
  return result;
}

```

## disassembly

```asm
0x18000a950  mov     [rsp+arg_8], rbx
0x18000a955  mov     [rsp+arg_10], rbp
0x18000a95a  push    rsi
0x18000a95b  push    rdi
0x18000a95c  push    r12
0x18000a95e  push    r13
0x18000a960  push    r15
0x18000a962  sub     rsp, 20h
0x18000a966  xor     r12d, r12d
0x18000a969  mov     r15, r9
0x18000a96c  mov     [r9], r12
0x18000a96f  mov     r13, r8
0x18000a972  mov     rdi, rdx
0x18000a975  mov     rbx, rcx
0x18000a978  call    cs:__imp_GetProcessHeap
0x18000a97e  xor     edx, edx; dwFlags
0x18000a980  mov     r8d, 58h ; 'X'; dwBytes
0x18000a986  mov     rcx, rax; hHeap
0x18000a989  call    cs:__imp_HeapAlloc
0x18000a98f  mov     [rsp+48h+arg_18], rax
0x18000a994  mov     rsi, rax
0x18000a997  test    rax, rax
0x18000a99a  jz      loc_18000AAD4
0x18000a9a0  mov     dword ptr [rsi+8], 5
0x18000a9a7  lea     rax, ??_7MMNotification_Event@@6B@; const MMNotification_Event::`vftable'
0x18000a9ae  mov     [rsi], rax
0x18000a9b1  mov     [rsi+10h], r12
0x18000a9b5  mov     [rsi+18h], r12
0x18000a9b9  mov     [rsi+30h], r12
0x18000a9bd  mov     [rsi+50h], rbx
0x18000a9c1  test    rsi, rsi
0x18000a9c4  jz      loc_18000AAD4
0x18000a9ca  test    rdi, rdi
0x18000a9cd  jz      loc_18000AB48
0x18000a9d3  mov     [rsp+48h+arg_0], r14
0x18000a9d8  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a9df  nop
0x18000a9e0  inc     rbx
0x18000a9e3  cmp     [rdi+rbx*2], r12w
0x18000a9e8  jnz     short loc_18000A9E0
0x18000a9ea  lea     r14, [rbx+1]
0x18000a9ee  mov     [rsi+10h], r12
0x18000a9f2  cmp     r14, rbx
0x18000a9f5  jb      loc_18000AACD
0x18000a9fb  mov     eax, 2
0x18000aa00  mul     r14
0x18000aa03  test    rdx, rdx
0x18000aa06  jnz     loc_18000AACD
0x18000aa0c  mov     rcx, rax; cb
0x18000aa0f  call    cs:__imp_CoTaskMemAlloc
0x18000aa15  mov     [rsi+10h], rax
0x18000aa19  mov     r10, rax
0x18000aa1c  test    rax, rax
0x18000aa1f  jnz     loc_18000AAF2
0x18000aa25  mov     ebp, 8007000Eh
0x18000aa2a  test    ebp, ebp
0x18000aa2c  js      short loc_18000AA9E
0x18000aa2e  test    r10, r10
0x18000aa31  jz      loc_18000AB24
0x18000aa37  cmp     r14, 7FFFFFFFh
0x18000aa3e  ja      loc_18000AB2D
0x18000aa44  cmp     rbx, 7FFFFFFFh
0x18000aa4b  jnb     loc_18000AB36
0x18000aa51  test    r14, r14
0x18000aa54  jz      short loc_18000AA9E
0x18000aa56  mov     rdx, r14
0x18000aa59  mov     r8, r10
0x18000aa5c  mov     rcx, r12
0x18000aa5f  nop
0x18000aa60  test    rbx, rbx
0x18000aa63  jz      short loc_18000AA85
0x18000aa65  movzx   eax, word ptr [rdi]
0x18000aa68  test    ax, ax
0x18000aa6b  jz      short loc_18000AA85
0x18000aa6d  mov     [r8], ax
0x18000aa71  add     rdi, 2
0x18000aa75  add     r8, 2
0x18000aa79  dec     rbx
0x18000aa7c  inc     rcx
0x18000aa7f  sub     rdx, 1
0x18000aa83  jnz     short loc_18000AA60
0x18000aa85  lea     r9, [rcx-1]
0x18000aa89  test    rdx, rdx
0x18000aa8c  cmovnz  r9, rcx
0x18000aa90  lea     rcx, [r8-2]
0x18000aa94  cmovnz  rcx, r8
0x18000aa98  mov     [rcx], r12w
0x18000aa9c  jnz     short loc_18000AAFA
0x18000aa9e  mov     r14, [rsp+48h+arg_0]
0x18000aaa3  test    ebp, ebp
0x18000aaa5  jns     short loc_18000AADB
0x18000aaa7  mov     edx, 1; unsigned int
0x18000aaac  mov     rcx, rsi; this
0x18000aaaf  call    ??_GMMNotification_Event@@UEAAPEAXI@Z; MMNotification_Event::`scalar deleting destructor'(uint)
0x18000aab4  mov     eax, ebp
0x18000aab6  mov     rbx, [rsp+48h+arg_8]
0x18000aabb  mov     rbp, [rsp+48h+arg_10]
0x18000aac0  add     rsp, 20h
0x18000aac4  pop     r15
0x18000aac6  pop     r13
0x18000aac8  pop     r12
0x18000aaca  pop     rdi
0x18000aacb  pop     rsi
0x18000aacc  retn
0x18000aacd  mov     ebp, 80070216h
0x18000aad2  jmp     short loc_18000AA9E
0x18000aad4  mov     eax, 8007000Eh
0x18000aad9  jmp     short loc_18000AAB6
0x18000aadb  mov     eax, [r13+10h]
0x18000aadf  movaps  xmm0, xmmword ptr [r13+0]
0x18000aae4  movups  xmmword ptr [rsi+38h], xmm0
0x18000aae8  mov     [rsi+48h], eax
0x18000aaeb  mov     eax, ebp
0x18000aaed  mov     [r15], rsi
0x18000aaf0  jmp     short loc_18000AAB6
0x18000aaf2  mov     ebp, r12d
0x18000aaf5  jmp     loc_18000AA2A
0x18000aafa  sub     r14, r9
0x18000aafd  cmp     r14, 1
0x18000ab01  jbe     short loc_18000AA9E
0x18000ab03  lea     r8, [r14+r14]
0x18000ab07  cmp     r8, 2
0x18000ab0b  jbe     short loc_18000AA9E
0x18000ab0d  inc     r9
0x18000ab10  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000ab14  xor     edx, edx; Val
0x18000ab16  lea     rcx, [r10+r9*2]; void *
0x18000ab1a  call    memset_0
0x18000ab1f  jmp     loc_18000AA9E
0x18000ab24  test    r14, r14
0x18000ab27  jz      loc_18000AA37
0x18000ab2d  mov     [rax], r12w
0x18000ab31  jmp     loc_18000AA9E
0x18000ab36  test    r14, r14
0x18000ab39  jz      loc_18000AA9E
0x18000ab3f  mov     [rax], r12w
0x18000ab43  jmp     loc_18000AA9E
0x18000ab48  mov     ebp, r12d
0x18000ab4b  jmp     loc_18000AAA3
```
