# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1400101f8`
- end: `0x140010427`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, HRESULT, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010684`

## callees

- `0x140001714`
- `0x1400101f8`
- `0x140010430`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140010267`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140010267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010276`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140010328`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140010328`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(
        __int64 a1,
        HRESULT a2,
        __int64 a3)
{
  void *v4; // rax
  HANDLE *v5; // rsi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v8; // edi
  void (__fastcall **v9)(HANDLE *); // rax
  char v10; // di
  __int64 v11; // rcx
  unsigned int v12; // edi
  HANDLE *v13; // rcx
  HANDLE pHandles[4]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v16; // [rsp+80h] [rbp+28h] BYREF
  HRESULT v17; // [rsp+88h] [rbp+30h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+38h] BYREF
  HANDLE *v19; // [rsp+98h] [rbp+40h]

  dwindex = a3;
  v17 = a2;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v19 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v17 = -2147024882;
    goto LABEL_25;
  }
  v5 = (HANDLE *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>'::`2'::FTMEventDelegate::FTMEventDelegate(v4);
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v5[7] = Event;
  if ( Event )
  {
    v9 = (void (__fastcall **)(HANDLE *))*v5;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = (void (__fastcall **)(HANDLE *))*v5;
    if ( v8 < 0 )
    {
      v9[2](v5);
      v17 = v8;
      goto LABEL_25;
    }
  }
  v9[1](v5);
  v19 = v5;
  (*((void (__fastcall **)(HANDLE *))*v5 + 2))(v5);
  v17 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)a1 + 48LL))(a1, v19);
  if ( v17 >= 0 )
  {
    pHandles[0] = v19[7];
    pHandles[1] = 0;
    v10 = 0;
    LODWORD(dwindex) = 0;
    v17 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v17 >= 0 && (_DWORD)dwindex )
    {
      v17 = -2147023673;
      v10 = 1;
    }
    v16 = 0;
    if ( v10
      && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))a1)(a1, &GUID_00000036_0000_0000_c000_000000000046, &v16) >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 72LL))(v16);
    }
    if ( v17 >= 0
      && *((_DWORD *)v19 + 12) != 1
      && (v16
       || (**(int (__fastcall ***)(__int64, GUID *, __int64 *))a1)(a1, &GUID_00000036_0000_0000_c000_000000000046, &v16) >= 0) )
    {
      (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v16 + 64LL))(v16, &v17);
    }
    v11 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
LABEL_25:
  v12 = v17;
  v13 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*((void (__fastcall **)(HANDLE *))*v13 + 2))(v13);
  }
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v12;
}

```

## disassembly

```asm
0x1400101f8  mov     [rsp-20h+dwindex], r8
0x1400101fd  mov     [rsp-20h+arg_8], edx
0x140010201  push    rbp
0x140010202  push    rbx
0x140010203  push    rsi
0x140010204  push    rdi
0x140010205  mov     rbp, rsp
0x140010208  sub     rsp, 58h
0x14001020c  mov     rbx, rcx
0x14001020f  mov     [rbp+var_28], rcx
0x140010213  test    rcx, rcx
0x140010216  jz      short loc_140010225
0x140010218  mov     rax, [rcx]
0x14001021b  mov     rax, [rax+8]
0x14001021f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010224  nop
0x140010225  mov     [rbp+arg_18], 0
0x14001022d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010234  mov     ecx, 40h ; '@'; unsigned __int64
0x140010239  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001023e  test    rax, rax
0x140010241  jnz     short loc_14001024F
0x140010243  mov     [rbp+arg_8], 8007000Eh
0x14001024a  jmp     loc_1400103E6
0x14001024f  mov     rcx, rax
0x140010252  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x140010257  mov     rsi, rax
0x14001025a  mov     r9d, 1F0003h; dwDesiredAccess
0x140010260  xor     r8d, r8d; dwFlags
0x140010263  xor     edx, edx; lpName
0x140010265  xor     ecx, ecx; lpEventAttributes
0x140010267  call    cs:__imp_CreateEventExW
0x14001026d  mov     [rsi+38h], rax
0x140010271  test    rax, rax
0x140010274  jnz     short loc_1400102A7
0x140010276  call    cs:__imp_GetLastError
0x14001027c  mov     edi, eax
0x14001027e  test    eax, eax
0x140010280  jle     short loc_14001028B
0x140010282  movzx   edi, ax
0x140010285  or      edi, 80070000h
0x14001028b  mov     rax, [rsi]
0x14001028e  test    edi, edi
0x140010290  jns     short loc_1400102AA
0x140010292  mov     rcx, rsi
0x140010295  mov     rax, [rax+10h]
0x140010299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001029e  nop
0x14001029f  mov     [rbp+arg_8], edi
0x1400102a2  jmp     loc_1400103E6
0x1400102a7  mov     rax, [rsi]
0x1400102aa  mov     rcx, rsi
0x1400102ad  mov     rax, [rax+8]
0x1400102b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102b6  nop
0x1400102b7  mov     [rbp+arg_18], rsi
0x1400102bb  mov     rax, [rsi]
0x1400102be  mov     rcx, rsi
0x1400102c1  mov     rax, [rax+10h]
0x1400102c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102ca  nop
0x1400102cb  mov     [rbp+arg_8], 0
0x1400102d2  mov     rax, [rbx]
0x1400102d5  mov     rdx, [rbp+arg_18]
0x1400102d9  mov     rcx, rbx
0x1400102dc  mov     rax, [rax+30h]
0x1400102e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102e5  mov     [rbp+arg_8], eax
0x1400102e8  test    eax, eax
0x1400102ea  js      loc_1400103E6
0x1400102f0  mov     rax, [rbp+arg_18]
0x1400102f4  mov     rcx, [rax+38h]
0x1400102f8  mov     [rbp+pHandles], rcx
0x1400102fc  mov     [rbp+var_18], 0
0x140010304  xor     dil, dil
0x140010307  mov     dword ptr [rbp+dwindex], 0
0x14001030e  lea     rax, [rbp+dwindex]
0x140010312  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x140010317  lea     r9, [rbp+pHandles]; pHandles
0x14001031b  mov     r8d, 1; cHandles
0x140010321  or      edx, 0FFFFFFFFh; dwTimeout
0x140010324  lea     ecx, [r8+7]; dwFlags
0x140010328  call    cs:__imp_CoWaitForMultipleHandles
0x14001032e  mov     [rbp+arg_8], eax
0x140010331  test    eax, eax
0x140010333  js      short loc_140010345
0x140010335  cmp     dword ptr [rbp+dwindex], 0
0x140010339  jz      short loc_140010345
0x14001033b  mov     [rbp+arg_8], 800704C7h
0x140010342  mov     dil, 1
0x140010345  mov     [rbp+arg_0], 0
0x14001034d  test    dil, dil
0x140010350  jz      short loc_14001037F
0x140010352  mov     rax, [rbx]
0x140010355  lea     r8, [rbp+arg_0]
0x140010359  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x140010360  mov     rcx, rbx
0x140010363  mov     rax, [rax]
0x140010366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001036b  test    eax, eax
0x14001036d  js      short loc_14001037F
0x14001036f  mov     rcx, [rbp+arg_0]
0x140010373  mov     rax, [rcx]
0x140010376  mov     rax, [rax+48h]
0x14001037a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001037f  cmp     [rbp+arg_8], 0
0x140010383  jl      short loc_1400103C8
0x140010385  mov     rax, [rbp+arg_18]
0x140010389  cmp     dword ptr [rax+30h], 1
0x14001038d  jz      short loc_1400103C8
0x14001038f  cmp     [rbp+arg_0], 0
0x140010394  jnz     short loc_1400103B3
0x140010396  mov     rax, [rbx]
0x140010399  lea     r8, [rbp+arg_0]
0x14001039d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1400103a4  mov     rcx, rbx
0x1400103a7  mov     rax, [rax]
0x1400103aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103af  test    eax, eax
0x1400103b1  js      short loc_1400103C8
0x1400103b3  mov     rcx, [rbp+arg_0]
0x1400103b7  mov     rax, [rcx]
0x1400103ba  lea     rdx, [rbp+arg_8]
0x1400103be  mov     rax, [rax+40h]
0x1400103c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103c7  nop
0x1400103c8  mov     rcx, [rbp+arg_0]
0x1400103cc  test    rcx, rcx
0x1400103cf  jz      short loc_1400103E6
0x1400103d1  mov     [rbp+arg_0], 0
0x1400103d9  mov     rax, [rcx]
0x1400103dc  mov     rax, [rax+10h]
0x1400103e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103e5  nop
0x1400103e6  mov     edi, [rbp+arg_8]
0x1400103e9  mov     rcx, [rbp+arg_18]
0x1400103ed  test    rcx, rcx
0x1400103f0  jz      short loc_140010407
0x1400103f2  mov     [rbp+arg_18], 0
0x1400103fa  mov     rax, [rcx]
0x1400103fd  mov     rax, [rax+10h]
0x140010401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010406  nop
0x140010407  test    rbx, rbx
0x14001040a  jz      short loc_14001041C
0x14001040c  mov     rcx, [rbx]
0x14001040f  mov     rax, [rcx+10h]
0x140010413  mov     rcx, rbx
0x140010416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001041b  nop
0x14001041c  mov     eax, edi
0x14001041e  add     rsp, 58h
0x140010422  pop     rdi
0x140010423  pop     rsi
0x140010424  pop     rbx
0x140010425  pop     rbp
0x140010426  retn
```
