# BCallOEMDevMode(void *,void *,_OEM_PLUGIN_ENTRY *,ulong,_devicemodeW *,_devicemodeW *,_OEM_DMEXTRAHEADER *,_OEM_DMEXTRAHEADER *)

- ea: `0x18003136c`
- end: `0x180031486`
- name: `?BCallOEMDevMode@@YAHPEAX0PEAU_OEM_PLUGIN_ENTRY@@KPEAU_devicemodeW@@2PEAU_OEM_DMEXTRAHEADER@@3@Z`
- size: `282`
- prototype: `__int64 __fastcall(void *, void *, struct _OEM_PLUGIN_ENTRY *, unsigned int, struct _devicemodeW *, struct _devicemodeW *, struct _OEM_DMEXTRAHEADER *, struct _OEM_DMEXTRAHEADER *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800034bc`
- `0x180031dec`
- `0x180032054`

## callees

- `0x18003136c`
- `0x1800321e4`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall BCallOEMDevMode(
        void *a1,
        void *a2,
        struct _OEM_PLUGIN_ENTRY *a3,
        unsigned int a4,
        struct _devicemodeW *a5,
        struct _devicemodeW *a6,
        struct _OEM_DMEXTRAHEADER *a7,
        struct _OEM_DMEXTRAHEADER *a8)
{
  __int64 v8; // rax
  int v11; // r8d
  __int64 v12; // rcx
  unsigned int (__fastcall *v13)(_QWORD, _DWORD *); // rax
  int v14; // eax
  _DWORD v16[2]; // [rsp+20h] [rbp-58h] BYREF
  void *v17; // [rsp+28h] [rbp-50h]
  void *v18; // [rsp+30h] [rbp-48h]
  __int64 v19; // [rsp+38h] [rbp-40h]
  struct _devicemodeW *v20; // [rsp+40h] [rbp-38h]
  struct _devicemodeW *v21; // [rsp+48h] [rbp-30h]
  struct _OEM_DMEXTRAHEADER *v22; // [rsp+50h] [rbp-28h]
  struct _OEM_DMEXTRAHEADER *v23; // [rsp+58h] [rbp-20h]
  int v24; // [rsp+60h] [rbp-18h]
  int v25; // [rsp+64h] [rbp-14h]

  v8 = *((_QWORD *)a3 + 4);
  v16[1] = 0;
  v25 = 0;
  if ( v8 )
  {
    v11 = *((_DWORD *)a3 + 16);
    if ( v11 )
    {
      v19 = v8;
      v20 = a6;
      v18 = a1;
      v12 = *((_QWORD *)a3 + 9);
      v21 = a5;
      v22 = a8;
      v16[0] = 72;
      v17 = a2;
      v23 = a7;
      v24 = v11;
      if ( v12 )
      {
        if ( (*((_QWORD *)a3 + 10) != *(_QWORD *)&IID_IPrintOemPS.Data1
           || *((_QWORD *)a3 + 11) != *(_QWORD *)IID_IPrintOemPS.Data4)
          && (*((_QWORD *)a3 + 10) != *(_QWORD *)&IID_IPrintOemPS2.Data1
           || *((_QWORD *)a3 + 11) != *(_QWORD *)IID_IPrintOemPS2.Data4)
          || (*(int (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v12 + 32LL))(v12, a4, v16) < 0 )
        {
          return 0;
        }
      }
      else
      {
        if ( (*((_BYTE *)a3 + 100) & 2) != 0 )
          v13 = (unsigned int (__fastcall *)(_QWORD, _DWORD *))*((_QWORD *)a3 + 14);
        else
          v13 = (unsigned int (__fastcall *)(_QWORD, _DWORD *))PGetOemEntrypointAddress((__int64)a3, 1u);
        if ( !v13 || !v13(a4, v16) )
          return 0;
      }
      v14 = *((_DWORD *)a3 + 16);
      if ( a7->dwSize != v14 || v24 != v14 || a7->dwSignature != *((_DWORD *)a3 + 6) )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18003136c  push    rbp
0x18003136e  push    rbx
0x18003136f  push    rsi
0x180031370  push    rdi
0x180031371  mov     rbp, rsp
0x180031374  sub     rsp, 78h
0x180031378  mov     rax, [r8+20h]
0x18003137c  mov     esi, r9d
0x18003137f  mov     [rbp+var_54], 0
0x180031386  mov     rbx, r8
0x180031389  mov     [rbp+var_14], 0
0x180031390  test    rax, rax
0x180031393  jz      loc_180031477
0x180031399  mov     r8d, [r8+40h]
0x18003139d  test    r8d, r8d
0x1800313a0  jz      loc_180031477
0x1800313a6  mov     rdi, [rbp+arg_30]
0x1800313aa  mov     [rbp+var_40], rax
0x1800313ae  mov     rax, [rbp+arg_28]
0x1800313b2  mov     [rbp+var_38], rax
0x1800313b6  mov     rax, [rbp+arg_20]
0x1800313ba  mov     [rbp+var_48], rcx
0x1800313be  mov     rcx, [rbx+48h]
0x1800313c2  mov     [rbp+var_30], rax
0x1800313c6  mov     rax, [rbp+arg_38]
0x1800313ca  mov     [rbp+var_28], rax
0x1800313ce  mov     [rbp+var_58], 48h ; 'H'
0x1800313d5  mov     [rbp+var_50], rdx
0x1800313d9  mov     [rbp+var_20], rdi
0x1800313dd  mov     [rbp+var_18], r8d
0x1800313e1  test    rcx, rcx
0x1800313e4  jz      short loc_180031432
0x1800313e6  mov     rax, [rbx+50h]
0x1800313ea  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x1800313f1  jnz     short loc_180031400
0x1800313f3  mov     rax, [rbx+58h]
0x1800313f7  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x1800313fe  jz      short loc_18003141A
0x180031400  mov     rax, [rbx+50h]
0x180031404  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18003140b  jnz     short loc_180031473
0x18003140d  mov     rax, [rbx+58h]
0x180031411  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x180031418  jnz     short loc_180031473
0x18003141a  mov     rax, [rcx]
0x18003141d  lea     r8, [rbp+var_58]
0x180031421  mov     edx, esi
0x180031423  mov     rax, [rax+20h]
0x180031427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003142c  test    eax, eax
0x18003142e  js      short loc_180031473
0x180031430  jmp     short loc_18003145F
0x180031432  test    byte ptr [rbx+64h], 2
0x180031436  jz      short loc_18003143E
0x180031438  mov     rax, [rbx+70h]
0x18003143c  jmp     short loc_18003144B
0x18003143e  mov     edx, 1
0x180031443  mov     rcx, rbx
0x180031446  call    PGetOemEntrypointAddress
0x18003144b  test    rax, rax
0x18003144e  jz      short loc_180031473
0x180031450  lea     rdx, [rbp+var_58]
0x180031454  mov     ecx, esi
0x180031456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003145b  test    eax, eax
0x18003145d  jz      short loc_180031473
0x18003145f  mov     eax, [rbx+40h]
0x180031462  cmp     [rdi], eax
0x180031464  jnz     short loc_180031473
0x180031466  cmp     [rbp+var_18], eax
0x180031469  jnz     short loc_180031473
0x18003146b  mov     eax, [rbx+18h]
0x18003146e  cmp     [rdi+4], eax
0x180031471  jz      short loc_180031477
0x180031473  xor     eax, eax
0x180031475  jmp     short loc_18003147C
0x180031477  mov     eax, 1
0x18003147c  add     rsp, 78h
0x180031480  pop     rdi
0x180031481  pop     rsi
0x180031482  pop     rbx
0x180031483  pop     rbp
0x180031484  retn
```
