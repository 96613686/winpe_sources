# _EventTypeFromIDAssetPair(ushort const *,_SebiEventType *,ushort * *)

- ea: `0x180032338`
- end: `0x180032431`
- name: `?_EventTypeFromIDAssetPair@@YAJPEBGPEAW4_SebiEventType@@PEAPEAG@Z`
- size: `249`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum _SebiEventType *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800327a4`

## callees

- `0x180032000`
- `0x180032338`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180032397`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180032397`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800323ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800323ea`

## pseudocode

```c
__int64 __fastcall _EventTypeFromIDAssetPair(
        const unsigned __int16 *a1,
        enum _SebiEventType *a2,
        unsigned __int16 **a3)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v5; // rbp
  unsigned int v8; // ebx
  unsigned int i; // esi
  unsigned __int64 v10; // r8
  const unsigned __int16 *v11; // rbp
  unsigned __int64 v12; // rsi
  unsigned __int16 *v13; // rcx
  unsigned __int16 **v15; // [rsp+20h] [rbp-68h]
  unsigned __int64 *v16; // [rsp+28h] [rbp-60h]
  unsigned int v17; // [rsp+30h] [rbp-58h]

  v3 = -1;
  v5 = -1;
  v8 = -2147023728;
  do
    ++v5;
  while ( a1[v5] );
  for ( i = 0; i < 2; ++i )
  {
    v10 = (unsigned __int64)*(&off_180047A90 + 3 * (int)i + 1);
    if ( v5 > v10 && !(unsigned int)_o__wcsnicmp(a1, (&off_180047A90)[3 * (int)i], v10 - 1) )
    {
      *(_DWORD *)a2 = (&off_180047A90)[3 * (int)i + 1];
      v11 = (&off_180047A90)[3 * (int)i];
      do
        ++v3;
      while ( v11[v3] );
      v12 = v3 + 1;
      *a3 = 0;
      if ( v3 + 1 >= v3 && is_mul_ok(v12, 2u) )
      {
        v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12);
        *a3 = v13;
        v8 = v13 == 0 ? 0x8007000E : 0;
        if ( v13 )
          StringCchCopyNExW(v13, v3 + 1, v11, v3, v15, v16, v17);
      }
      else
      {
        return (unsigned int)-2147024362;
      }
      return v8;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180032338  push    rbx
0x18003233a  push    rbp
0x18003233b  push    rsi
0x18003233c  push    rdi
0x18003233d  push    r12
0x18003233f  push    r13
0x180032341  push    r14
0x180032343  push    r15
0x180032345  sub     rsp, 48h
0x180032349  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003234d  mov     r15, rcx
0x180032350  mov     rbp, rdi
0x180032353  xor     ecx, ecx
0x180032355  mov     r12, r8
0x180032358  mov     r13, rdx
0x18003235b  mov     ebx, 80070490h
0x180032360  inc     rbp
0x180032363  cmp     [r15+rbp*2], cx
0x180032368  jnz     short loc_180032360
0x18003236a  mov     esi, ecx
0x18003236c  lea     rcx, off_180047A90; "PrintNotificationHandler"
0x180032373  cmp     esi, 2
0x180032376  jnb     loc_18003241E
0x18003237c  movsxd  rax, esi
0x18003237f  lea     r14, [rax+rax*2]
0x180032383  mov     r8, [rcx+r14*8+8]
0x180032388  cmp     rbp, r8
0x18003238b  jbe     short loc_1800323AA
0x18003238d  mov     rdx, [rcx+r14*8]
0x180032391  dec     r8
0x180032394  mov     rcx, r15
0x180032397  call    cs:__imp__o__wcsnicmp
0x18003239d  xor     ecx, ecx
0x18003239f  test    eax, eax
0x1800323a1  jz      short loc_1800323AE
0x1800323a3  lea     rcx, off_180047A90; "PrintNotificationHandler"
0x1800323aa  inc     esi
0x1800323ac  jmp     short loc_180032373
0x1800323ae  lea     rbp, off_180047A90; "PrintNotificationHandler"
0x1800323b5  mov     eax, [rbp+r14*8+10h]
0x1800323ba  mov     [r13+0], eax
0x1800323be  mov     rbp, [rbp+r14*8+0]
0x1800323c3  inc     rdi
0x1800323c6  cmp     [rbp+rdi*2+0], cx
0x1800323cb  jnz     short loc_1800323C3
0x1800323cd  lea     rsi, [rdi+1]
0x1800323d1  mov     [r12], rcx
0x1800323d5  cmp     rsi, rdi
0x1800323d8  jb      short loc_180032419
0x1800323da  mov     eax, 2
0x1800323df  mul     rsi
0x1800323e2  test    rdx, rdx
0x1800323e5  jnz     short loc_180032419
0x1800323e7  mov     rcx, rax; cb
0x1800323ea  call    cs:__imp_CoTaskMemAlloc
0x1800323f0  mov     rcx, rax; unsigned __int16 *
0x1800323f3  mov     [r12], rax
0x1800323f7  neg     rax
0x1800323fa  sbb     ebx, ebx
0x1800323fc  not     ebx
0x1800323fe  and     ebx, 8007000Eh
0x180032404  test    rcx, rcx
0x180032407  jz      short loc_18003241E
0x180032409  mov     r9, rdi; unsigned __int64
0x18003240c  mov     r8, rbp; unsigned __int16 *
0x18003240f  mov     rdx, rsi; unsigned __int64
0x180032412  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180032417  jmp     short loc_18003241E
0x180032419  mov     ebx, 80070216h
0x18003241e  mov     eax, ebx
0x180032420  add     rsp, 48h
0x180032424  pop     r15
0x180032426  pop     r14
0x180032428  pop     r13
0x18003242a  pop     r12
0x18003242c  pop     rdi
0x18003242d  pop     rsi
0x18003242e  pop     rbp
0x18003242f  pop     rbx
0x180032430  retn
```
