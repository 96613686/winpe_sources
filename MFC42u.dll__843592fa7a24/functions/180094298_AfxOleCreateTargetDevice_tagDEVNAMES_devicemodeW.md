# _AfxOleCreateTargetDevice(tagDEVNAMES *,_devicemodeW *)

- ea: `0x180094298`
- end: `0x180094402`
- name: `?_AfxOleCreateTargetDevice@@YAPEAUtagDVTARGETDEVICE@@PEAUtagDEVNAMES@@PEAU_devicemodeW@@@Z`
- size: `362`
- prototype: `struct tagDVTARGETDEVICE *__fastcall(struct tagDEVNAMES *, struct _devicemodeW *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180094408`
- `0x1800b1520`
- `0x1800b3390`

## callees

- `0x180094298`
- `0x180094c50`
- `0x1800d1f7a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009436e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009436e`
- `KERNEL32!lstrcpyW` at `0x18009438c`
- `KERNEL32!lstrcpyW` at `0x1800943a5`
- `KERNEL32!lstrcpyW` at `0x1800943be`
- `KERNEL32!lstrcpyW` at `0x18009438c`
- `KERNEL32!lstrcpyW` at `0x1800943a5`
- `KERNEL32!lstrcpyW` at `0x1800943be`

## pseudocode

```c
struct tagDVTARGETDEVICE *__fastcall _AfxOleCreateTargetDevice(struct tagDEVNAMES *a1, struct _devicemodeW *a2)
{
  int v2; // r14d
  const unsigned __int16 *v4; // rdi
  const unsigned __int16 *v5; // rsi
  const unsigned __int16 *v6; // rbp
  int v7; // r12d
  int v8; // r15d
  unsigned int v9; // edx
  unsigned int v10; // r8d
  unsigned int v11; // eax
  unsigned int v12; // r13d
  _WORD *v13; // rax
  _WORD *v14; // rbx
  unsigned __int16 v15; // r12
  unsigned __int16 v16; // r15
  unsigned __int16 v17; // r14

  v2 = 0;
  if ( a1->wDriverOffset )
    v4 = (const unsigned __int16 *)a1 + a1->wDriverOffset;
  else
    v4 = 0;
  if ( a1->wDeviceOffset )
    v5 = (const unsigned __int16 *)a1 + a1->wDeviceOffset;
  else
    v5 = 0;
  if ( a1->wOutputOffset )
    v6 = (const unsigned __int16 *)a1 + a1->wOutputOffset;
  else
    v6 = 0;
  if ( v4 )
    v7 = 2 * ocslen(v4) + 2;
  else
    v7 = 0;
  if ( v5 )
    v8 = 2 * ocslen(v5) + 2;
  else
    v8 = 0;
  if ( v6 )
    v2 = 2 * ocslen(v6) + 2;
  v9 = v7 + v2 + v8;
  v10 = a2->dmDriverExtra + a2->dmSize;
  v11 = v10 + v9;
  if ( v10 + v9 < v9 )
    return 0;
  if ( v11 < v10 )
    return 0;
  v12 = v11 + 16;
  if ( v11 + 16 < v11 )
    return 0;
  v13 = CoTaskMemAlloc(v12);
  v14 = v13;
  if ( v13 )
  {
    *(_DWORD *)v13 = v12;
    v13[2] = 16;
    lstrcpyW(v13 + 8, v4);
    v15 = v14[2] + v7;
    v14[3] = v15;
    lstrcpyW((_WORD *)((char *)v14 + v15), v5);
    v16 = v14[3] + v8;
    v14[4] = v16;
    lstrcpyW((_WORD *)((char *)v14 + v16), v6);
    v17 = v14[4] + v2;
    v14[5] = v17;
    memcpy_0((char *)v14 + v17, a2, a2->dmDriverExtra + 220LL);
  }
  return (struct tagDVTARGETDEVICE *)v14;
}

```

## disassembly

```asm
0x180094298  mov     [rsp+Src], rdx
0x18009429d  push    rbx
0x18009429e  push    rbp
0x18009429f  push    rsi
0x1800942a0  push    rdi
0x1800942a1  push    r12
0x1800942a3  push    r13
0x1800942a5  push    r14
0x1800942a7  push    r15
0x1800942a9  sub     rsp, 28h
0x1800942ad  xor     r14d, r14d
0x1800942b0  mov     rbx, rdx
0x1800942b3  cmp     [rcx], r14w
0x1800942b7  jnz     short loc_1800942BE
0x1800942b9  mov     edi, r14d
0x1800942bc  jmp     short loc_1800942C5
0x1800942be  movzx   eax, word ptr [rcx]
0x1800942c1  lea     rdi, [rcx+rax*2]
0x1800942c5  cmp     [rcx+2], r14w
0x1800942ca  jnz     short loc_1800942D1
0x1800942cc  mov     rsi, r14
0x1800942cf  jmp     short loc_1800942D9
0x1800942d1  movzx   eax, word ptr [rcx+2]
0x1800942d5  lea     rsi, [rcx+rax*2]
0x1800942d9  cmp     [rcx+4], r14w
0x1800942de  jnz     short loc_1800942E5
0x1800942e0  mov     rbp, r14
0x1800942e3  jmp     short loc_1800942ED
0x1800942e5  movzx   eax, word ptr [rcx+4]
0x1800942e9  lea     rbp, [rcx+rax*2]
0x1800942ed  test    rdi, rdi
0x1800942f0  jnz     short loc_1800942F7
0x1800942f2  mov     r12d, r14d
0x1800942f5  jmp     short loc_180094307
0x1800942f7  mov     rcx, rdi; unsigned __int16 *
0x1800942fa  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x1800942ff  lea     r12d, ds:2[rax*2]
0x180094307  test    rsi, rsi
0x18009430a  jnz     short loc_180094311
0x18009430c  mov     r15d, r14d
0x18009430f  jmp     short loc_180094321
0x180094311  mov     rcx, rsi; unsigned __int16 *
0x180094314  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180094319  lea     r15d, ds:2[rax*2]
0x180094321  test    rbp, rbp
0x180094324  jz      short loc_180094336
0x180094326  mov     rcx, rbp; unsigned __int16 *
0x180094329  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18009432e  lea     r14d, ds:2[rax*2]
0x180094336  movzx   eax, word ptr [rbx+46h]
0x18009433a  lea     edx, [r14+r15]
0x18009433e  movzx   r8d, word ptr [rbx+44h]
0x180094343  add     edx, r12d
0x180094346  add     r8d, eax
0x180094349  lea     eax, [r8+rdx]
0x18009434d  cmp     eax, edx
0x18009434f  jb      loc_1800943EF
0x180094355  cmp     eax, r8d
0x180094358  jb      loc_1800943EF
0x18009435e  lea     r13d, [rax+10h]
0x180094362  cmp     r13d, eax
0x180094365  jb      loc_1800943EF
0x18009436b  mov     ecx, r13d; cb
0x18009436e  call    cs:__imp_CoTaskMemAlloc
0x180094374  mov     rbx, rax
0x180094377  test    rax, rax
0x18009437a  jz      short loc_1800943EA
0x18009437c  lea     rcx, [rax+10h]; lpString1
0x180094380  mov     [rax], r13d
0x180094383  mov     rdx, rdi; lpString2
0x180094386  mov     word ptr [rax+4], 10h
0x18009438c  call    cs:__imp_lstrcpyW
0x180094392  add     r12w, [rbx+4]
0x180094397  mov     rdx, rsi; lpString2
0x18009439a  movzx   ecx, r12w
0x18009439e  mov     [rbx+6], cx
0x1800943a2  add     rcx, rbx; lpString1
0x1800943a5  call    cs:__imp_lstrcpyW
0x1800943ab  add     r15w, [rbx+6]
0x1800943b0  mov     rdx, rbp; lpString2
0x1800943b3  movzx   ecx, r15w
0x1800943b7  mov     [rbx+8], cx
0x1800943bb  add     rcx, rbx; lpString1
0x1800943be  call    cs:__imp_lstrcpyW
0x1800943c4  mov     rdx, [rsp+68h+Src]; Src
0x1800943c9  add     r14w, [rbx+8]
0x1800943ce  movzx   ecx, r14w
0x1800943d2  mov     [rbx+0Ah], cx
0x1800943d6  add     rcx, rbx; void *
0x1800943d9  movzx   r8d, word ptr [rdx+46h]
0x1800943de  add     r8, 0DCh; Size
0x1800943e5  call    memcpy_0
0x1800943ea  mov     rax, rbx
0x1800943ed  jmp     short loc_1800943F1
0x1800943ef  xor     eax, eax
0x1800943f1  add     rsp, 28h
0x1800943f5  pop     r15
0x1800943f7  pop     r14
0x1800943f9  pop     r13
0x1800943fb  pop     r12
0x1800943fd  pop     rdi
0x1800943fe  pop     rsi
0x1800943ff  pop     rbp
0x180094400  pop     rbx
0x180094401  retn
```
