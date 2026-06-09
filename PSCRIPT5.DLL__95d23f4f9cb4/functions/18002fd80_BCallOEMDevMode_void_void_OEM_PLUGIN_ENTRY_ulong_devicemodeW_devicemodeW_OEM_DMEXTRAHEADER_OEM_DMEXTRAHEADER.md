# BCallOEMDevMode(void *,void *,_OEM_PLUGIN_ENTRY *,ulong,_devicemodeW *,_devicemodeW *,_OEM_DMEXTRAHEADER *,_OEM_DMEXTRAHEADER *)

- ea: `0x18002fd80`
- end: `0x18002fe99`
- name: `?BCallOEMDevMode@@YAHPEAX0PEAU_OEM_PLUGIN_ENTRY@@KPEAU_devicemodeW@@2PEAU_OEM_DMEXTRAHEADER@@3@Z`
- size: `281`
- prototype: `__int64 __fastcall(void *, void *, struct _OEM_PLUGIN_ENTRY *, unsigned int, struct _devicemodeW *, struct _devicemodeW *, struct _OEM_DMEXTRAHEADER *, struct _OEM_DMEXTRAHEADER *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800033f4`
- `0x1800307cc`
- `0x180030a2c`

## callees

- `0x18002fd80`
- `0x180030bcc`
- `0x18005d010`

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
          v13 = (unsigned int (__fastcall *)(_QWORD, _DWORD *))PGetOemEntrypointAddress(a3, 1);
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
0x18002fd80  push    rbp
0x18002fd82  push    rbx
0x18002fd83  push    rsi
0x18002fd84  push    rdi
0x18002fd85  mov     rbp, rsp
0x18002fd88  sub     rsp, 78h
0x18002fd8c  mov     rax, [r8+20h]
0x18002fd90  mov     esi, r9d
0x18002fd93  mov     [rbp+var_54], 0
0x18002fd9a  mov     rbx, r8
0x18002fd9d  mov     [rbp+var_14], 0
0x18002fda4  test    rax, rax
0x18002fda7  jz      loc_18002FE8B
0x18002fdad  mov     r8d, [r8+40h]
0x18002fdb1  test    r8d, r8d
0x18002fdb4  jz      loc_18002FE8B
0x18002fdba  mov     rdi, [rbp+arg_30]
0x18002fdbe  mov     [rbp+var_40], rax
0x18002fdc2  mov     rax, [rbp+arg_28]
0x18002fdc6  mov     [rbp+var_38], rax
0x18002fdca  mov     rax, [rbp+arg_20]
0x18002fdce  mov     [rbp+var_48], rcx
0x18002fdd2  mov     rcx, [rbx+48h]
0x18002fdd6  mov     [rbp+var_30], rax
0x18002fdda  mov     rax, [rbp+arg_38]
0x18002fdde  mov     [rbp+var_28], rax
0x18002fde2  mov     [rbp+var_58], 48h ; 'H'
0x18002fde9  mov     [rbp+var_50], rdx
0x18002fded  mov     [rbp+var_20], rdi
0x18002fdf1  mov     [rbp+var_18], r8d
0x18002fdf5  test    rcx, rcx
0x18002fdf8  jz      short loc_18002FE46
0x18002fdfa  mov     rax, [rbx+50h]
0x18002fdfe  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x18002fe05  jnz     short loc_18002FE14
0x18002fe07  mov     rax, [rbx+58h]
0x18002fe0b  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x18002fe12  jz      short loc_18002FE2E
0x18002fe14  mov     rax, [rbx+50h]
0x18002fe18  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18002fe1f  jnz     short loc_18002FE87
0x18002fe21  mov     rax, [rbx+58h]
0x18002fe25  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18002fe2c  jnz     short loc_18002FE87
0x18002fe2e  mov     rax, [rcx]
0x18002fe31  lea     r8, [rbp+var_58]
0x18002fe35  mov     edx, esi
0x18002fe37  mov     rax, [rax+20h]
0x18002fe3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe40  test    eax, eax
0x18002fe42  js      short loc_18002FE87
0x18002fe44  jmp     short loc_18002FE73
0x18002fe46  test    byte ptr [rbx+64h], 2
0x18002fe4a  jz      short loc_18002FE52
0x18002fe4c  mov     rax, [rbx+70h]
0x18002fe50  jmp     short loc_18002FE5F
0x18002fe52  mov     edx, 1
0x18002fe57  mov     rcx, rbx
0x18002fe5a  call    PGetOemEntrypointAddress
0x18002fe5f  test    rax, rax
0x18002fe62  jz      short loc_18002FE87
0x18002fe64  lea     rdx, [rbp+var_58]
0x18002fe68  mov     ecx, esi
0x18002fe6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe6f  test    eax, eax
0x18002fe71  jz      short loc_18002FE87
0x18002fe73  mov     eax, [rbx+40h]
0x18002fe76  cmp     [rdi], eax
0x18002fe78  jnz     short loc_18002FE87
0x18002fe7a  cmp     [rbp+var_18], eax
0x18002fe7d  jnz     short loc_18002FE87
0x18002fe7f  mov     eax, [rbx+18h]
0x18002fe82  cmp     [rdi+4], eax
0x18002fe85  jz      short loc_18002FE8B
0x18002fe87  xor     eax, eax
0x18002fe89  jmp     short loc_18002FE90
0x18002fe8b  mov     eax, 1
0x18002fe90  add     rsp, 78h
0x18002fe94  pop     rdi
0x18002fe95  pop     rsi
0x18002fe96  pop     rbx
0x18002fe97  pop     rbp
0x18002fe98  retn
```
