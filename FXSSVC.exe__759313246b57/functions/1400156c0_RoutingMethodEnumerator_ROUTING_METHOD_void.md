# RoutingMethodEnumerator(_ROUTING_METHOD *,void *)

- ea: `0x1400156c0`
- end: `0x1400159ef`
- name: `?RoutingMethodEnumerator@@YAHPEAU_ROUTING_METHOD@@PEAX@Z`
- size: `815`
- prototype: `__int64 __fastcall(struct _ROUTING_METHOD *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1400156c0`
- `0x1400259bc`
- `0x14006aec0`
- `0x14008b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14001580f`
- `ole32!CoTaskMemFree` at `0x14001580f`
- `ole32!StringFromIID` at `0x1400156f9`
- `ole32!StringFromIID` at `0x14001583a`
- `ole32!StringFromIID` at `0x1400156f9`
- `ole32!StringFromIID` at `0x14001583a`

## pseudocode

```c
__int64 __fastcall RoutingMethodEnumerator(struct _ROUTING_METHOD *a1, _DWORD *a2)
{
  void *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rax
  int v7; // edx
  int v8; // r9d
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  int v12; // r9d
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  int v16; // r10d
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  int v20; // r9d
  __int64 v21; // rax
  int v22; // eax
  int v23; // r8d
  __int64 *v25; // r15
  LPVOID pv; // [rsp+90h] [rbp+18h] BYREF
  char *v27; // [rsp+98h] [rbp+20h]

  pv = 0;
  if ( *a2 == 1 )
  {
    a2[1] += 64;
    StringFromIID((const IID *const)a1 + 2, (LPOLESTR *)&pv);
    v4 = pv;
    v5 = -1;
    if ( pv )
    {
      v6 = -1;
      do
        ++v6;
      while ( *((_WORD *)pv + v6) );
      v7 = 2 * v6 + 2;
    }
    else
    {
      v7 = 0;
    }
    v8 = v7 + a2[1];
    a2[1] = v8;
    v9 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 56LL);
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v9 + 2 * v10) );
      v11 = 2 * v10 + 2;
    }
    else
    {
      v11 = 0;
    }
    v12 = v11 + v8;
    a2[1] = v12;
    v13 = *((_QWORD *)a1 + 7);
    if ( v13 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(v13 + 2 * v14) );
      v15 = 2 * v14 + 2;
    }
    else
    {
      v15 = 0;
    }
    v16 = v15 + v12;
    a2[1] = v15 + v12;
    v17 = *((_QWORD *)a1 + 8);
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v17 + 2 * v18) );
      v19 = 2 * v18 + 2;
    }
    else
    {
      v19 = 0;
    }
    v20 = v19 + v16;
    a2[1] = v19 + v16;
    if ( *((_QWORD *)a1 + 11) == -572 )
    {
      v22 = 0;
    }
    else
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(*((_QWORD *)a1 + 11) + 572LL + 2 * v21) );
      v22 = 2 * v21 + 2;
    }
    a2[1] = v22 + v20;
    if ( *((_QWORD *)a1 + 11) == -52 )
    {
      v23 = 0;
    }
    else
    {
      do
        ++v5;
      while ( *(_WORD *)(*((_QWORD *)a1 + 11) + 52LL + 2 * v5) );
      v23 = 2 * v5 + 2;
    }
    a2[1] = v23 + v22 + v20;
    goto LABEL_32;
  }
  if ( *a2 == 2 )
  {
    StringFromIID((const IID *const)a1 + 2, (LPOLESTR *)&pv);
    v27 = (char *)(a2 + 1);
    v25 = (__int64 *)(a2 + 6);
    *(_DWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *((_QWORD *)a2 + 3)) = 64;
    *(_DWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *((_QWORD *)a2 + 3) + 4) = *(_DWORD *)(*((_QWORD *)a2 + 2) + 24LL);
    *(_DWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *v25 + 8) = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*((_QWORD *)a1 + 11) + 1656LL))(
                                                                             pv,
                                                                             *(unsigned int *)(*((_QWORD *)a2 + 2) + 24LL),
                                                                             -1);
    StoreString(
      *(unsigned __int16 **)(*((_QWORD *)a2 + 2) + 56LL),
      (_QWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *v25 + 16),
      *v25,
      (_QWORD *)a2 + 1,
      a2[8]);
    StoreString(
      (unsigned __int16 *)pv,
      (_QWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *v25 + 24),
      *v25,
      (_QWORD *)a2 + 1,
      a2[8]);
    StoreString(
      *((unsigned __int16 **)a1 + 8),
      (_QWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *v25 + 32),
      *v25,
      (_QWORD *)a2 + 1,
      a2[8]);
    StoreString(
      *((unsigned __int16 **)a1 + 7),
      (_QWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *v25 + 40),
      *v25,
      (_QWORD *)a2 + 1,
      a2[8]);
    StoreString(
      (unsigned __int16 *)(*((_QWORD *)a1 + 11) + 572LL),
      (_QWORD *)(((unsigned __int64)(unsigned int)a2[1] << 6) + *v25 + 48),
      *v25,
      (_QWORD *)a2 + 1,
      a2[8]);
    StoreString(
      (unsigned __int16 *)(*((_QWORD *)a1 + 11) + 52LL),
      (_QWORD *)(((unsigned __int64)(unsigned int)a2[1]++ << 6) + *v25 + 56),
      *v25,
      (_QWORD *)a2 + 1,
      a2[8]);
    v4 = pv;
LABEL_32:
    CoTaskMemFree(v4);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1400156c0  mov     rax, rsp
0x1400156c3  mov     [rax+10h], rdx
0x1400156c7  mov     [rax+8], rcx
0x1400156cb  push    rbx
0x1400156cc  push    rsi
0x1400156cd  push    rdi
0x1400156ce  push    r12
0x1400156d0  push    r14
0x1400156d2  push    r15
0x1400156d4  sub     rsp, 48h
0x1400156d8  mov     rdi, rdx
0x1400156db  mov     rsi, rcx
0x1400156de  xor     ebx, ebx
0x1400156e0  mov     [rax+18h], rbx
0x1400156e4  cmp     dword ptr [rdx], 1
0x1400156e7  jnz     loc_140015825
0x1400156ed  add     dword ptr [rdx+4], 40h ; '@'
0x1400156f1  add     rcx, 20h ; ' '; rclsid
0x1400156f5  lea     rdx, [rax+18h]; lplpsz
0x1400156f9  call    cs:__imp_StringFromIID
0x140015700  nop     dword ptr [rax+rax+00h]
0x140015705  mov     rcx, [rsp+78h+pv]; pv
0x14001570d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140015711  test    rcx, rcx
0x140015714  jz      short loc_14001572C
0x140015716  mov     rax, r8
0x140015719  inc     rax
0x14001571c  cmp     [rcx+rax*2], bx
0x140015720  jnz     short loc_140015719
0x140015722  lea     rdx, ds:2[rax*2]
0x14001572a  jmp     short loc_14001572F
0x14001572c  mov     rdx, rbx
0x14001572f  mov     r9d, [rdi+4]
0x140015733  add     r9d, edx
0x140015736  mov     [rdi+4], r9d
0x14001573a  mov     rax, [rdi+10h]
0x14001573e  mov     rdx, [rax+38h]
0x140015742  test    rdx, rdx
0x140015745  jz      short loc_14001575D
0x140015747  mov     rax, r8
0x14001574a  inc     rax
0x14001574d  cmp     [rdx+rax*2], bx
0x140015751  jnz     short loc_14001574A
0x140015753  lea     rax, ds:2[rax*2]
0x14001575b  jmp     short loc_140015760
0x14001575d  mov     rax, rbx
0x140015760  add     r9d, eax
0x140015763  mov     [rdi+4], r9d
0x140015767  mov     rdx, [rsi+38h]
0x14001576b  test    rdx, rdx
0x14001576e  jz      short loc_140015786
0x140015770  mov     rax, r8
0x140015773  inc     rax
0x140015776  cmp     [rdx+rax*2], bx
0x14001577a  jnz     short loc_140015773
0x14001577c  lea     rax, ds:2[rax*2]
0x140015784  jmp     short loc_140015789
0x140015786  mov     rax, rbx
0x140015789  lea     r10d, [rax+r9]
0x14001578d  mov     [rdi+4], r10d
0x140015791  mov     rdx, [rsi+40h]
0x140015795  test    rdx, rdx
0x140015798  jz      short loc_1400157B0
0x14001579a  mov     rax, r8
0x14001579d  inc     rax
0x1400157a0  cmp     [rdx+rax*2], bx
0x1400157a4  jnz     short loc_14001579D
0x1400157a6  lea     rax, ds:2[rax*2]
0x1400157ae  jmp     short loc_1400157B3
0x1400157b0  mov     rax, rbx
0x1400157b3  lea     r9d, [rax+r10]
0x1400157b7  mov     [rdi+4], r9d
0x1400157bb  mov     rdx, [rsi+58h]
0x1400157bf  add     rdx, 23Ch
0x1400157c6  jz      short loc_1400157DE
0x1400157c8  mov     rax, r8
0x1400157cb  inc     rax
0x1400157ce  cmp     [rdx+rax*2], bx
0x1400157d2  jnz     short loc_1400157CB
0x1400157d4  lea     rax, ds:2[rax*2]
0x1400157dc  jmp     short loc_1400157E1
0x1400157de  mov     rax, rbx
0x1400157e1  lea     edx, [rax+r9]
0x1400157e5  mov     [rdi+4], edx
0x1400157e8  mov     rax, [rsi+58h]
0x1400157ec  add     rax, 34h ; '4'
0x1400157f0  jz      short loc_140015806
0x1400157f2  inc     r8
0x1400157f5  cmp     [rax+r8*2], bx
0x1400157fa  jnz     short loc_1400157F2
0x1400157fc  lea     r8, ds:2[r8*2]
0x140015804  jmp     short loc_140015809
0x140015806  mov     r8, rbx
0x140015809  add     edx, r8d
0x14001580c  mov     [rdi+4], edx
0x14001580f  call    cs:__imp_CoTaskMemFree
0x140015816  nop     dword ptr [rax+rax+00h]
0x14001581b  mov     eax, 1
0x140015820  jmp     loc_1400159E0
0x140015825  cmp     dword ptr [rdx], 2
0x140015828  jnz     loc_1400159DE
0x14001582e  add     rcx, 20h ; ' '; rclsid
0x140015832  lea     rdx, [rsp+78h+pv]; lplpsz
0x14001583a  call    cs:__imp_StringFromIID
0x140015841  nop     dword ptr [rax+rax+00h]
0x140015846  lea     r14, [rdi+4]
0x14001584a  mov     [rsp+78h+arg_18], r14
0x140015852  lea     r15, [rdi+18h]
0x140015856  mov     [rsp+78h+var_40], r15
0x14001585b  mov     ecx, [r14]
0x14001585e  shl     rcx, 6
0x140015862  mov     rax, [r15]
0x140015865  mov     dword ptr [rcx+rax], 40h ; '@'
0x14001586c  lea     r12, [rdi+10h]
0x140015870  mov     [rsp+78h+var_48], r12
0x140015875  mov     rax, [r12]
0x140015879  mov     edx, [r14]
0x14001587c  shl     rdx, 6
0x140015880  mov     rcx, [r15]
0x140015883  mov     eax, [rax+18h]
0x140015886  mov     [rdx+rcx+4], eax
0x14001588a  mov     rax, [rsi+58h]
0x14001588e  mov     rdx, [r12]
0x140015892  or      r8, 0FFFFFFFFFFFFFFFFh
0x140015896  mov     edx, [rdx+18h]
0x140015899  mov     rcx, [rsp+78h+pv]
0x1400158a1  mov     rax, [rax+678h]
0x1400158a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400158ad  mov     edx, [r14]
0x1400158b0  shl     rdx, 6
0x1400158b4  mov     rcx, [r15]
0x1400158b7  mov     [rdx+rcx+8], eax
0x1400158bb  jmp     short loc_1400158DF
0x1400158bd  mov     rdi, [rsp+78h+arg_8]
0x1400158c5  mov     rsi, [rsp+78h+arg_0]
0x1400158cd  mov     r14, [rsp+78h+arg_18]
0x1400158d5  mov     r12, [rsp+78h+var_48]
0x1400158da  mov     r15, [rsp+78h+var_40]
0x1400158df  lea     rbx, [rdi+8]
0x1400158e3  mov     r8, [r15]
0x1400158e6  mov     eax, [r14]
0x1400158e9  shl     rax, 6
0x1400158ed  lea     rdx, [r8+10h]
0x1400158f1  add     rdx, rax
0x1400158f4  mov     rcx, [r12]
0x1400158f8  mov     eax, [rdi+20h]
0x1400158fb  mov     [rsp+78h+var_58], eax; int
0x1400158ff  mov     r9, rbx
0x140015902  mov     rcx, [rcx+38h]; unsigned __int16 *
0x140015906  call    StoreString
0x14001590b  mov     r8, [r15]
0x14001590e  mov     eax, [r14]
0x140015911  shl     rax, 6
0x140015915  lea     rdx, [r8+18h]
0x140015919  add     rdx, rax
0x14001591c  mov     eax, [rdi+20h]
0x14001591f  mov     [rsp+78h+var_58], eax; int
0x140015923  mov     r9, rbx
0x140015926  mov     rcx, [rsp+78h+pv]; unsigned __int16 *
0x14001592e  call    StoreString
0x140015933  mov     r8, [r15]
0x140015936  mov     eax, [r14]
0x140015939  shl     rax, 6
0x14001593d  lea     rdx, [r8+20h]
0x140015941  add     rdx, rax
0x140015944  mov     eax, [rdi+20h]
0x140015947  mov     [rsp+78h+var_58], eax; int
0x14001594b  mov     r9, rbx
0x14001594e  mov     rcx, [rsi+40h]; unsigned __int16 *
0x140015952  call    StoreString
0x140015957  mov     r8, [r15]
0x14001595a  mov     eax, [r14]
0x14001595d  shl     rax, 6
0x140015961  lea     rdx, [r8+28h]
0x140015965  add     rdx, rax
0x140015968  mov     eax, [rdi+20h]
0x14001596b  mov     [rsp+78h+var_58], eax; int
0x14001596f  mov     r9, rbx
0x140015972  mov     rcx, [rsi+38h]; unsigned __int16 *
0x140015976  call    StoreString
0x14001597b  mov     r8, [r15]
0x14001597e  mov     eax, [r14]
0x140015981  shl     rax, 6
0x140015985  lea     rdx, [r8+30h]
0x140015989  add     rdx, rax
0x14001598c  mov     rcx, [rsi+58h]
0x140015990  add     rcx, 23Ch; unsigned __int16 *
0x140015997  mov     eax, [rdi+20h]
0x14001599a  mov     [rsp+78h+var_58], eax; int
0x14001599e  mov     r9, rbx
0x1400159a1  call    StoreString
0x1400159a6  mov     r8, [r15]
0x1400159a9  mov     eax, [r14]
0x1400159ac  shl     rax, 6
0x1400159b0  lea     rdx, [r8+38h]
0x1400159b4  add     rdx, rax
0x1400159b7  mov     rcx, [rsi+58h]
0x1400159bb  add     rcx, 34h ; '4'; unsigned __int16 *
0x1400159bf  mov     eax, [rdi+20h]
0x1400159c2  mov     [rsp+78h+var_58], eax; int
0x1400159c6  mov     r9, rbx
0x1400159c9  call    StoreString
0x1400159ce  inc     dword ptr [r14]
0x1400159d1  mov     rcx, [rsp+78h+pv]
0x1400159d9  jmp     loc_14001580F
0x1400159de  xor     eax, eax
0x1400159e0  add     rsp, 48h
0x1400159e4  pop     r15
0x1400159e6  pop     r14
0x1400159e8  pop     r12
0x1400159ea  pop     rdi
0x1400159eb  pop     rsi
0x1400159ec  pop     rbx
0x1400159ed  retn
0x14008746a  push    rbp
0x14008746c  sub     rsp, 30h
0x140087470  mov     rbp, rdx
0x140087473  mov     r8, [rcx]
0x140087476  mov     r8d, [r8]
0x140087479  mov     rax, [rbp+80h]
0x140087480  mov     rdx, [rax+58h]
0x140087484  add     rdx, 34h ; '4'
0x140087488  mov     ecx, 2
0x14008748d  call    ?HandleFaxExtensionFault@@YAJW4EXCEPTION_SOURCE_TYPE@@PEBGK@Z; HandleFaxExtensionFault(EXCEPTION_SOURCE_TYPE,ushort const *,ulong)
0x140087492  nop
0x140087493  add     rsp, 30h
0x140087497  pop     rbp
0x140087498  retn
```
