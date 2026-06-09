# BValidateAndMergeDevmodeWithOemPlugins

- ea: `0x180032054`
- end: `0x1800321db`
- name: `BValidateAndMergeDevmodeWithOemPlugins`
- size: `391`
- prototype: `__int64 __fastcall(struct _devicemodeW *, unsigned int, __int64, struct _RAWBINARYDATA *, __int64, __int64, int, struct _devicemodeW *, struct _OEM_PLUGINS *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800034bc`

## callees

- `0x180029d7c`
- `0x180031004`
- `0x18003136c`
- `0x180031654`
- `0x180032054`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800321b5`
- `KERNEL32!LocalFree` at `0x1800321b5`

## pseudocode

```c
__int64 __fastcall BValidateAndMergeDevmodeWithOemPlugins(
        struct _devicemodeW *a1,
        unsigned int a2,
        __int64 a3,
        struct _RAWBINARYDATA *a4,
        __int64 a5,
        const wchar_t *a6,
        int a7,
        struct _devicemodeW *a8,
        struct _OEM_PLUGINS *a9,
        void *a10)
{
  struct _devicemodeW *v10; // rdi
  __int64 v16; // r9
  struct _OEM_PLUGINS *v17; // r14
  struct _devicemodeW *v18; // rax
  struct _devicemodeW *v19; // rsi
  unsigned int v20; // ebx
  int v21; // edi
  __int64 v22; // rax
  struct _OEM_DMEXTRAHEADER *v23; // r15
  struct _OEM_DMEXTRAHEADER *v24; // rbp
  struct _OEM_PLUGIN_ENTRY *v25; // rbx
  __int64 v26; // rax
  unsigned int v27[18]; // [rsp+40h] [rbp-48h] BYREF

  v10 = a8;
  v27[0] = 0;
  if ( !a8 )
    return 1;
  a7 = 0;
  if ( (int)IsRawBinaryDataFromGPD((__int64)a4, &a7) < 0 )
    return 0;
  if ( a7 )
    return 0;
  v17 = a9;
  v18 = PConvertToCurrentVersionDevmodeWithOemPlugins(a10, a2, a4, v16, v10, a1, a9, v27);
  v19 = v18;
  if ( !v18 )
    return 0;
  v20 = PSBMergeDriverDevmode((__int64)a1, a2, a3, a4, a5, a6, (__int64)v18, v10);
  if ( v20 && v27[0] )
  {
    v21 = *((_DWORD *)v17 + 2);
    if ( !v21 )
    {
LABEL_15:
      v20 = 1;
      goto LABEL_16;
    }
    v22 = a2 + 976;
    v23 = (struct _OEM_DMEXTRAHEADER *)((char *)v19 + v22);
    v24 = (struct _OEM_DMEXTRAHEADER *)((char *)a1 + v22);
    v25 = (struct _OEM_PLUGINS *)((char *)v17 + 24);
    while ( 1 )
    {
      if ( *((_QWORD *)v25 + 4) )
      {
        if ( !(unsigned int)BCallOEMDevMode(a10, *(void **)v17, v25, 4u, a1, v19, v24, v23) )
        {
          v20 = 0;
          break;
        }
        if ( *((_DWORD *)v25 + 16) )
        {
          v26 = *((unsigned int *)v25 + 16);
          *((_QWORD *)v25 + 7) = v24;
          v24 = (struct _OEM_DMEXTRAHEADER *)((char *)v24 + v26);
          v23 = (struct _OEM_DMEXTRAHEADER *)((char *)v23 + v26);
        }
      }
      v25 = (struct _OEM_PLUGIN_ENTRY *)((char *)v25 + 176);
      if ( !--v21 )
        goto LABEL_15;
    }
  }
LABEL_16:
  LocalFree(v19);
  return v20;
}

```

## disassembly

```asm
0x180032054  push    rbx
0x180032056  push    rbp
0x180032057  push    rsi
0x180032058  push    rdi
0x180032059  push    r12
0x18003205b  push    r14
0x18003205d  push    r15
0x18003205f  sub     rsp, 50h
0x180032063  mov     rdi, [rsp+88h+arg_38]
0x18003206b  mov     rbx, r9
0x18003206e  mov     [rsp+88h+var_48], 0
0x180032076  mov     r15, r8
0x180032079  mov     ebp, edx
0x18003207b  mov     r12, rcx
0x18003207e  test    rdi, rdi
0x180032081  jnz     short loc_18003208B
0x180032083  lea     eax, [rdi+1]
0x180032086  jmp     loc_1800321CB
0x18003208b  lea     rdx, [rsp+88h+arg_30]
0x180032093  mov     [rsp+88h+arg_30], 0
0x18003209e  mov     rcx, rbx
0x1800320a1  call    IsRawBinaryDataFromGPD
0x1800320a6  test    eax, eax
0x1800320a8  js      loc_1800321C9
0x1800320ae  cmp     [rsp+88h+arg_30], 0
0x1800320b6  jnz     loc_1800321C9
0x1800320bc  mov     r14, [rsp+88h+arg_40]
0x1800320c4  lea     rax, [rsp+88h+var_48]
0x1800320c9  mov     rcx, [rsp+88h+arg_48]; void *
0x1800320d1  mov     r8, rbx; struct _RAWBINARYDATA *
0x1800320d4  mov     [rsp+88h+var_50], rax; unsigned int *
0x1800320d9  mov     edx, ebp; unsigned int
0x1800320db  mov     [rsp+88h+var_58], r14; struct _OEM_PLUGINS *
0x1800320e0  mov     [rsp+88h+var_60], r12; struct _devicemodeW *
0x1800320e5  mov     [rsp+88h+var_68], rdi; struct _devicemodeW *
0x1800320ea  call    ?PConvertToCurrentVersionDevmodeWithOemPlugins@@YAPEAU_devicemodeW@@PEAXKPEAU_RAWBINARYDATA@@KPEAU1@2PEAU_OEM_PLUGINS@@PEAK@Z; PConvertToCurrentVersionDevmodeWithOemPlugins(void *,ulong,_RAWBINARYDATA *,ulong,_devicemodeW *,_devicemodeW *,_OEM_PLUGINS *,ulong *)
0x1800320ef  mov     rsi, rax
0x1800320f2  test    rax, rax
0x1800320f5  jz      loc_1800321C9
0x1800320fb  mov     rcx, [rsp+88h+arg_28]
0x180032103  mov     r9, rbx
0x180032106  mov     [rsp+88h+var_50], rdi
0x18003210b  mov     r8, r15
0x18003210e  mov     [rsp+88h+var_58], rax
0x180032113  mov     edx, ebp
0x180032115  mov     [rsp+88h+var_60], rcx
0x18003211a  mov     rcx, [rsp+88h+arg_20]
0x180032122  mov     [rsp+88h+var_68], rcx
0x180032127  mov     rcx, r12
0x18003212a  call    PSBMergeDriverDevmode
0x18003212f  mov     ebx, eax
0x180032131  test    eax, eax
0x180032133  jz      short loc_1800321B2
0x180032135  cmp     [rsp+88h+var_48], 0
0x18003213a  jz      short loc_1800321B2
0x18003213c  mov     edi, [r14+8]
0x180032140  test    edi, edi
0x180032142  jz      short loc_1800321AD
0x180032144  lea     eax, [rbp+3D0h]
0x18003214a  lea     r15, [rax+rsi]
0x18003214e  lea     rbp, [rax+r12]
0x180032152  lea     rbx, [r14+18h]
0x180032156  cmp     qword ptr [rbx+20h], 0
0x18003215b  jz      short loc_1800321A1
0x18003215d  mov     rdx, [r14]; void *
0x180032160  mov     r9d, 4; unsigned int
0x180032166  mov     rcx, [rsp+88h+arg_48]; void *
0x18003216e  mov     r8, rbx; struct _OEM_PLUGIN_ENTRY *
0x180032171  mov     [rsp+88h+var_50], r15; struct _OEM_DMEXTRAHEADER *
0x180032176  mov     [rsp+88h+var_58], rbp; struct _OEM_DMEXTRAHEADER *
0x18003217b  mov     [rsp+88h+var_60], rsi; struct _devicemodeW *
0x180032180  mov     [rsp+88h+var_68], r12; struct _devicemodeW *
0x180032185  call    ?BCallOEMDevMode@@YAHPEAX0PEAU_OEM_PLUGIN_ENTRY@@KPEAU_devicemodeW@@2PEAU_OEM_DMEXTRAHEADER@@3@Z; BCallOEMDevMode(void *,void *,_OEM_PLUGIN_ENTRY *,ulong,_devicemodeW *,_devicemodeW *,_OEM_DMEXTRAHEADER *,_OEM_DMEXTRAHEADER *)
0x18003218a  test    eax, eax
0x18003218c  jz      short loc_1800321C5
0x18003218e  cmp     dword ptr [rbx+40h], 0
0x180032192  jz      short loc_1800321A1
0x180032194  mov     eax, [rbx+40h]
0x180032197  mov     [rbx+38h], rbp
0x18003219b  add     rbp, rax
0x18003219e  add     r15, rax
0x1800321a1  add     rbx, 0B0h
0x1800321a8  add     edi, 0FFFFFFFFh
0x1800321ab  jnz     short loc_180032156
0x1800321ad  mov     ebx, 1
0x1800321b2  mov     rcx, rsi; hMem
0x1800321b5  call    cs:__imp_LocalFree
0x1800321bc  nop     dword ptr [rax+rax+00h]
0x1800321c1  mov     eax, ebx
0x1800321c3  jmp     short loc_1800321CB
0x1800321c5  xor     ebx, ebx
0x1800321c7  jmp     short loc_1800321B2
0x1800321c9  xor     eax, eax
0x1800321cb  add     rsp, 50h
0x1800321cf  pop     r15
0x1800321d1  pop     r14
0x1800321d3  pop     r12
0x1800321d5  pop     rdi
0x1800321d6  pop     rsi
0x1800321d7  pop     rbp
0x1800321d8  pop     rbx
0x1800321d9  retn
```
