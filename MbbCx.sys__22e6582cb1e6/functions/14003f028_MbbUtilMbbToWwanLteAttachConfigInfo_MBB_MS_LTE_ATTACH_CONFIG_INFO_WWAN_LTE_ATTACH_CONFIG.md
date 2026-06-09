# MbbUtilMbbToWwanLteAttachConfigInfo(_MBB_MS_LTE_ATTACH_CONFIG_INFO *,_WWAN_LTE_ATTACH_CONFIG *)

- ea: `0x14003f028`
- end: `0x14003f1f4`
- name: `?MbbUtilMbbToWwanLteAttachConfigInfo@@YAXPEAU_MBB_MS_LTE_ATTACH_CONFIG_INFO@@PEAU_WWAN_LTE_ATTACH_CONFIG@@@Z`
- size: `460`
- prototype: `void __fastcall(struct _MBB_MS_LTE_ATTACH_CONFIG_INFO *, struct _WWAN_LTE_ATTACH_CONFIG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14002fb40`

## callees

- `0x140001cf8`
- `0x14003f028`
- `0x140048040`
- `0x140048340`

## pseudocode

```c
void __fastcall MbbUtilMbbToWwanLteAttachConfigInfo(
        struct _MBB_MS_LTE_ATTACH_CONFIG_INFO *a1,
        struct _WWAN_LTE_ATTACH_CONFIG *a2)
{
  __int64 i; // r14
  __int64 v5; // r12
  __int64 v6; // r15
  int v7; // edx
  __int64 v8; // rax
  unsigned __int64 v9; // rdx
  int v10; // ecx
  __int64 v11; // rax
  int v12; // ecx

  for ( i = 0; (unsigned int)i < *(_DWORD *)a1; *(_DWORD *)((char *)a2 + v6 + 1264) = v12 )
  {
    v5 = *((unsigned int *)a1 + 2 * i + 1);
    v6 = 1268LL * (unsigned int)i;
    *(_DWORD *)((char *)a2 + v6 + 4) = 0;
    *(_DWORD *)((char *)a2 + v6 + 8) = 14;
    *(_DWORD *)((char *)a2 + v6 + 1240) = *(_DWORD *)((char *)a1 + v5 + 36);
    *(_DWORD *)((char *)a2 + v6 + 1244) = *(_DWORD *)((char *)a1 + v5 + 40);
    memset((char *)a2 + v6 + 12, 0, 0xCAu);
    memmove(
      (char *)a2 + v6 + 12,
      (char *)a1 + v5 + *(unsigned int *)((char *)a1 + v5 + 12),
      *(unsigned int *)((char *)a1 + v5 + 16));
    memset((char *)a2 + v6 + 214, 0, 0x200u);
    memmove(
      (char *)a2 + v6 + 214,
      (char *)a1 + v5 + *(unsigned int *)((char *)a1 + v5 + 20),
      *(unsigned int *)((char *)a1 + v5 + 24));
    memset((char *)a2 + v6 + 726, 0, 0x200u);
    memmove(
      (char *)a2 + v6 + 726,
      (char *)a1 + v5 + *(unsigned int *)((char *)a1 + v5 + 28),
      *(unsigned int *)((char *)a1 + v5 + 32));
    v8 = *(int *)((char *)a1 + v5);
    if ( (unsigned int)v8 > 4 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 3;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          9,
          60,
          (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids);
      }
      v10 = 0;
      v9 = 0x140000000uLL;
    }
    else
    {
      v9 = 0x140000000uLL;
      v10 = dword_140057A30[v8];
    }
    *(_DWORD *)((char *)a2 + v6 + 1248) = v10;
    *(_DWORD *)((char *)a2 + v6 + 1256) = *(_DWORD *)((char *)a1 + v5 + 4);
    v11 = *(int *)((char *)a1 + v5 + 8);
    if ( (unsigned int)v11 > 4 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 3;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          9,
          61,
          (__int64)&WPP_36f7929d0c593a29047f269d453c8817_Traceguids);
      }
      v12 = 6;
    }
    else
    {
      v12 = dword_140057A18[v11];
    }
    i = (unsigned int)(i + 1);
  }
}

```

## disassembly

```asm
0x14003f028  push    rbx
0x14003f02a  push    rbp
0x14003f02b  push    rsi
0x14003f02c  push    rdi
0x14003f02d  push    r12
0x14003f02f  push    r13
0x14003f031  push    r14
0x14003f033  push    r15
0x14003f035  sub     rsp, 38h
0x14003f039  xor     r14d, r14d
0x14003f03c  mov     rbp, rdx
0x14003f03f  mov     rsi, rcx
0x14003f042  cmp     [rcx], r14d
0x14003f045  jbe     loc_14003F1E2
0x14003f04b  lea     r13, WPP_RECORDER_INITIALIZED
0x14003f052  mov     r12d, [rsi+r14*8+4]
0x14003f057  xor     edx, edx; Val
0x14003f059  mov     eax, r14d
0x14003f05c  mov     r8d, 0CAh; Size
0x14003f062  imul    r15, rax, 4F4h
0x14003f069  lea     rdi, [r12+rsi]
0x14003f06d  mov     dword ptr [r15+rbp+4], 0
0x14003f076  lea     rbx, [r15+rbp]
0x14003f07a  mov     dword ptr [r15+rbp+8], 0Eh
0x14003f083  lea     rcx, [rbx+0Ch]; void *
0x14003f087  mov     eax, [rsi+r12+24h]
0x14003f08c  mov     [r15+rbp+4D8h], eax
0x14003f094  mov     eax, [rsi+r12+28h]
0x14003f099  mov     [r15+rbp+4DCh], eax
0x14003f0a1  call    memset
0x14003f0a6  mov     edx, [rsi+r12+0Ch]
0x14003f0ab  lea     rcx, [rbx+0Ch]; void *
0x14003f0af  mov     r8d, [rsi+r12+10h]; Size
0x14003f0b4  add     rdx, rdi; Src
0x14003f0b7  call    memmove
0x14003f0bc  lea     rbx, [r15+rbp]
0x14003f0c0  xor     edx, edx; Val
0x14003f0c2  lea     rcx, [rbx+0D6h]; void *
0x14003f0c9  mov     r8d, 200h; Size
0x14003f0cf  call    memset
0x14003f0d4  mov     edx, [rsi+r12+14h]
0x14003f0d9  lea     rcx, [rbx+0D6h]; void *
0x14003f0e0  mov     r8d, [rsi+r12+18h]; Size
0x14003f0e5  add     rdx, rdi; Src
0x14003f0e8  call    memmove
0x14003f0ed  lea     rbx, [r15+rbp]
0x14003f0f1  xor     edx, edx; Val
0x14003f0f3  lea     rcx, [rbx+2D6h]; void *
0x14003f0fa  mov     r8d, 200h; Size
0x14003f100  call    memset
0x14003f105  mov     edx, [rsi+r12+1Ch]
0x14003f10a  lea     rcx, [rbx+2D6h]; void *
0x14003f111  mov     r8d, [rsi+r12+20h]; Size
0x14003f116  add     rdx, rdi; Src
0x14003f119  call    memmove
0x14003f11e  movsxd  rax, dword ptr [rdi]
0x14003f121  cmp     eax, 4
0x14003f124  ja      short loc_14003F136
0x14003f126  lea     rdx, cs:140000000h
0x14003f12d  mov     ecx, ds:rva dword_140057A30[rdx+rax*4]
0x14003f134  jmp     short loc_14003F170
0x14003f136  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003f13d  jz      short loc_14003F167
0x14003f13f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f146  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003f14d  mov     r9d, 3Ch ; '<'
0x14003f153  mov     [rsp+78h+var_58], rax
0x14003f158  mov     dl, 3
0x14003f15a  mov     rcx, [rcx+40h]
0x14003f15e  lea     r8d, [r9-33h]
0x14003f162  call    WPP_RECORDER_SF_
0x14003f167  xor     ecx, ecx
0x14003f169  lea     rdx, cs:140000000h
0x14003f170  mov     [r15+rbp+4E0h], ecx
0x14003f178  mov     eax, [rsi+r12+4]
0x14003f17d  mov     [r15+rbp+4E8h], eax
0x14003f185  movsxd  rax, dword ptr [rsi+r12+8]
0x14003f18a  cmp     eax, 4
0x14003f18d  ja      short loc_14003F198
0x14003f18f  mov     ecx, ds:rva dword_140057A18[rdx+rax*4]
0x14003f196  jmp     short loc_14003F1CE
0x14003f198  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003f19f  jz      short loc_14003F1C9
0x14003f1a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f1a8  lea     rax, WPP_36f7929d0c593a29047f269d453c8817_Traceguids
0x14003f1af  mov     r9d, 3Dh ; '='
0x14003f1b5  mov     [rsp+78h+var_58], rax
0x14003f1ba  mov     dl, 3
0x14003f1bc  mov     rcx, [rcx+40h]
0x14003f1c0  lea     r8d, [r9-34h]
0x14003f1c4  call    WPP_RECORDER_SF_
0x14003f1c9  mov     ecx, 6
0x14003f1ce  inc     r14d
0x14003f1d1  mov     [r15+rbp+4F0h], ecx
0x14003f1d9  cmp     r14d, [rsi]
0x14003f1dc  jb      loc_14003F052
0x14003f1e2  add     rsp, 38h
0x14003f1e6  pop     r15
0x14003f1e8  pop     r14
0x14003f1ea  pop     r13
0x14003f1ec  pop     r12
0x14003f1ee  pop     rdi
0x14003f1ef  pop     rsi
0x14003f1f0  pop     rbp
0x14003f1f1  pop     rbx
0x14003f1f2  retn
```
