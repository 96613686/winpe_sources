# LogpInterfaceEvent(_GUID *,_GUID *,char *,char *,_EVENT_DESCRIPTOR *)

- ea: `0x180007fb0`
- end: `0x180008046`
- name: `?LogpInterfaceEvent@@YAXPEAU_GUID@@0PEAD1PEAU_EVENT_DESCRIPTOR@@@Z`
- size: `150`
- prototype: `void __fastcall(struct _GUID *, struct _GUID *, char *, char *, struct _EVENT_DESCRIPTOR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002350`
- `0x180002864`
- `0x180005b24`

## callees

- `0x180007fb0`
- `0x18000a980`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000802e`
- `ntdll!EtwEventWrite` at `0x18000802e`

## pseudocode

```c
void __fastcall LogpInterfaceEvent(
        struct _GUID *a1,
        struct _GUID *a2,
        char *a3,
        char *a4,
        struct _EVENT_DESCRIPTOR *a5)
{
  __int64 v5; // rcx
  __int64 v6; // rax
  _QWORD v7[5]; // [rsp+20h] [rbp-50h] BYREF
  int v8; // [rsp+48h] [rbp-28h]
  int v9; // [rsp+4Ch] [rbp-24h]
  char *v10; // [rsp+50h] [rbp-20h]
  int v11; // [rsp+58h] [rbp-18h]
  int v12; // [rsp+5Ch] [rbp-14h]

  v7[0] = a1;
  v5 = -1;
  v6 = -1;
  v7[1] = 16;
  v7[2] = a2;
  v7[3] = 16;
  v7[4] = a3;
  do
    ++v6;
  while ( a3[v6] );
  v9 = 0;
  v8 = v6 + 1;
  v10 = a4;
  do
    ++v5;
  while ( a4[v5] );
  v12 = 0;
  v11 = v5 + 1;
  ((void (__fastcall *)(__int64, struct _EVENT_DESCRIPTOR *, __int64, _QWORD *))EtwEventWrite)(
    g_EpmapEtwHandle,
    a5,
    4,
    v7);
}

```

## disassembly

```asm
0x180007fb0  push    rbp
0x180007fb2  mov     rbp, rsp
0x180007fb5  sub     rsp, 70h
0x180007fb9  mov     rax, cs:__security_cookie
0x180007fc0  xor     rax, rsp
0x180007fc3  mov     [rbp+var_10], rax
0x180007fc7  mov     r10, [rbp+arg_20]
0x180007fcb  xor     r11d, r11d
0x180007fce  mov     [rbp+var_50], rcx
0x180007fd2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007fd6  mov     rax, rcx
0x180007fd9  mov     [rbp+var_48], 10h
0x180007fe1  mov     [rbp+var_40], rdx
0x180007fe5  mov     [rbp+var_38], 10h
0x180007fed  mov     [rbp+var_30], r8
0x180007ff1  inc     rax
0x180007ff4  cmp     [r8+rax], r11b
0x180007ff8  jnz     short loc_180007FF1
0x180007ffa  inc     eax
0x180007ffc  mov     [rbp+var_24], r11d
0x180008000  mov     [rbp+var_28], eax
0x180008003  mov     [rbp+var_20], r9
0x180008007  inc     rcx
0x18000800a  cmp     [r9+rcx], r11b
0x18000800e  jnz     short loc_180008007
0x180008010  lea     eax, [rcx+1]
0x180008013  mov     [rbp+var_14], r11d
0x180008017  mov     rcx, cs:g_EpmapEtwHandle
0x18000801e  lea     r9, [rbp+var_50]
0x180008022  mov     r8d, 4
0x180008028  mov     [rbp+var_18], eax
0x18000802b  mov     rdx, r10
0x18000802e  call    cs:__imp_EtwEventWrite
0x180008034  mov     rcx, [rbp+var_10]
0x180008038  xor     rcx, rsp; StackCookie
0x18000803b  call    __security_check_cookie
0x180008040  add     rsp, 70h
0x180008044  pop     rbp
0x180008045  retn
```
