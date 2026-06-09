# GetAllStorageDevices

- ea: `0x1800071b0`
- end: `0x180007335`
- name: `GetAllStorageDevices`
- size: `389`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180007c90`
- `0x180007da8`
- `0x180008d20`

## callees

- `0x180006cd0`
- `0x180006eac`
- `0x1800071b0`
- `0x180007ef8`
- `0x18000aa8c`
- `0x18000e7f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800071d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800071d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072e4`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000722c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000722c`

## pseudocode

```c
__int64 __fastcall GetAllStorageDevices(void **a1)
{
  unsigned int v2; // r12d
  char *v3; // r15
  __int64 v4; // rbx
  int StorageDevices; // eax
  int v6; // r8d
  unsigned __int64 v7; // rbx
  char *v8; // rdi
  char *v9; // rdx
  size_t v10; // rbx
  unsigned __int64 v12; // rbp
  __int128 v13; // [rsp+30h] [rbp-68h] BYREF
  __int64 v14; // [rsp+40h] [rbp-58h]

  EnterCriticalSection(&CriticalSection);
  v2 = 0;
  v3 = (char *)Src;
  v4 = qword_180018DD8;
  if ( Src != (void *)qword_180018DD8 )
    goto LABEL_8;
  v13 = 0;
  v14 = 0;
  StorageDevices = GetStorageDevices((__int64)&v13, 0);
  if ( StorageDevices >= 0 )
  {
    StorageDevices = GetStorageDevices((__int64)&v13, 1u);
    if ( StorageDevices < 0 )
    {
      v6 = 383;
      goto LABEL_4;
    }
    std::vector<_STORAGE_DEVICE_DATA>::operator=(&Src, &v13);
    std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(&v13);
    v4 = qword_180018DD8;
    v3 = (char *)Src;
LABEL_8:
    if ( a1 == &Src )
      goto LABEL_13;
    v7 = 0xDAB7EC1DD3431B57uLL * ((v4 - (__int64)v3) >> 4);
    v8 = (char *)*a1;
    if ( v7 <= 0xDAB7EC1DD3431B57uLL * (((_BYTE *)a1[2] - (_BYTE *)*a1) >> 4) )
    {
      v12 = 0xDAB7EC1DD3431B57uLL * (((_BYTE *)a1[1] - v8) >> 4);
      if ( v7 > v12 )
      {
        memmove_0(*a1, v3, 16 * (((_BYTE *)a1[1] - v8) >> 4));
        v8 = (char *)a1[1];
        v7 -= v12;
        v9 = &v3[1648 * v12];
        goto LABEL_12;
      }
    }
    else
    {
      std::vector<_STORAGE_DEVICE_DATA>::_Clear_and_reserve_geometric(a1, v7);
      v8 = (char *)*a1;
    }
    v9 = v3;
LABEL_12:
    v10 = 1648 * v7;
    memmove_0(v8, v9, v10);
    a1[1] = &v8[v10];
    goto LABEL_13;
  }
  v6 = 382;
LABEL_4:
  v2 = ZTraceReportPropagationNoThis(StorageDevices, "GetAllStorageDevices", v6);
  std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(&v13);
LABEL_13:
  LeaveCriticalSection(&CriticalSection);
  return v2;
}

```

## disassembly

```asm
0x1800071b0  push    rbx
0x1800071b2  push    rbp
0x1800071b3  push    rsi
0x1800071b4  push    rdi
0x1800071b5  push    r12
0x1800071b7  push    r13
0x1800071b9  push    r14
0x1800071bb  push    r15
0x1800071bd  sub     rsp, 58h
0x1800071c1  mov     r14, rcx
0x1800071c4  lea     r13, CriticalSection
0x1800071cb  mov     [rsp+98h+var_78], r13
0x1800071d0  mov     rcx, r13; lpCriticalSection
0x1800071d3  call    cs:__imp_EnterCriticalSection
0x1800071d9  mov     [rsp+98h+var_70], 1
0x1800071de  xor     r12d, r12d
0x1800071e1  lea     rdi, Src
0x1800071e8  mov     r15, cs:Src
0x1800071ef  mov     rbx, cs:qword_180018DD8
0x1800071f6  cmp     r15, rbx
0x1800071f9  jnz     loc_180007285
0x1800071ff  xorps   xmm0, xmm0
0x180007202  movdqu  [rsp+98h+var_68], xmm0
0x180007208  mov     [rsp+98h+var_58], r12
0x18000720d  xor     edx, edx
0x18000720f  lea     rcx, [rsp+98h+var_68]
0x180007214  call    GetStorageDevices
0x180007219  test    eax, eax
0x18000721b  jns     short loc_180007244
0x18000721d  mov     r8d, 17Eh
0x180007223  lea     rdx, aGetallstoraged; "GetAllStorageDevices"
0x18000722a  mov     ecx, eax
0x18000722c  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007232  mov     r12d, eax
0x180007235  lea     rcx, [rsp+98h+var_68]
0x18000723a  call    ??1?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@QEAA@XZ; std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(void)
0x18000723f  jmp     loc_1800072E1
0x180007244  mov     edx, 1
0x180007249  lea     rcx, [rsp+98h+var_68]
0x18000724e  call    GetStorageDevices
0x180007253  test    eax, eax
0x180007255  jns     short loc_18000725F
0x180007257  mov     r8d, 17Fh
0x18000725d  jmp     short loc_180007223
0x18000725f  lea     rdx, [rsp+98h+var_68]
0x180007264  mov     rcx, rdi
0x180007267  call    ??4?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<_STORAGE_DEVICE_DATA>::operator=(std::vector<_STORAGE_DEVICE_DATA> &&)
0x18000726c  nop
0x18000726d  lea     rcx, [rsp+98h+var_68]
0x180007272  call    ??1?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@QEAA@XZ; std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(void)
0x180007277  mov     rbx, cs:qword_180018DD8
0x18000727e  mov     r15, cs:Src
0x180007285  cmp     r14, rdi
0x180007288  jz      short loc_1800072E1
0x18000728a  sub     rbx, r15
0x18000728d  sar     rbx, 4
0x180007291  mov     rcx, 0DAB7EC1DD3431B57h
0x18000729b  imul    rbx, rcx
0x18000729f  mov     rdi, [r14]
0x1800072a2  mov     rax, [r14+10h]
0x1800072a6  sub     rax, rdi
0x1800072a9  sar     rax, 4
0x1800072ad  imul    rax, rcx
0x1800072b1  cmp     rbx, rax
0x1800072b4  jbe     short loc_1800072FE
0x1800072b6  mov     rdx, rbx
0x1800072b9  mov     rcx, r14
0x1800072bc  call    ?_Clear_and_reserve_geometric@?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@AEAAX_K@Z; std::vector<_STORAGE_DEVICE_DATA>::_Clear_and_reserve_geometric(unsigned __int64)
0x1800072c1  mov     rdi, [r14]
0x1800072c4  mov     rdx, r15; Src
0x1800072c7  imul    rbx, 670h
0x1800072ce  mov     r8, rbx; Size
0x1800072d1  mov     rcx, rdi; void *
0x1800072d4  call    memmove_0
0x1800072d9  lea     rax, [rbx+rdi]
0x1800072dd  mov     [r14+8], rax
0x1800072e1  mov     rcx, r13; lpCriticalSection
0x1800072e4  call    cs:__imp_LeaveCriticalSection
0x1800072ea  mov     eax, r12d
0x1800072ed  add     rsp, 58h
0x1800072f1  pop     r15
0x1800072f3  pop     r14
0x1800072f5  pop     r13
0x1800072f7  pop     r12
0x1800072f9  pop     rdi
0x1800072fa  pop     rsi
0x1800072fb  pop     rbp
0x1800072fc  pop     rbx
0x1800072fd  retn
0x1800072fe  mov     rbp, [r14+8]
0x180007302  sub     rbp, rdi
0x180007305  sar     rbp, 4
0x180007309  imul    rbp, rcx
0x18000730d  cmp     rbx, rbp
0x180007310  jbe     short loc_1800072C4
0x180007312  imul    rsi, rbp, 670h
0x180007319  mov     r8, rsi; Size
0x18000731c  mov     rdx, r15; Src
0x18000731f  mov     rcx, rdi; void *
0x180007322  call    memmove_0
0x180007327  mov     rdi, [r14+8]
0x18000732b  sub     rbx, rbp
0x18000732e  lea     rdx, [rsi+r15]
0x180007332  jmp     short loc_1800072C7
```
