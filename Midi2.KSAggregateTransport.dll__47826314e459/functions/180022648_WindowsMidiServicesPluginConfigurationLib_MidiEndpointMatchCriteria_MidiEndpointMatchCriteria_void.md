# WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria(void)

- ea: `0x180022648`
- end: `0x180022832`
- name: `??1MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@QEAA@XZ`
- size: `490`
- prototype: `void __fastcall(WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180023320`
- `0x180024c84`
- `0x180036d5c`
- `0x180037fec`
- `0x180039c00`
- `0x18004e280`
- `0x18005b154`
- `0x18005bc17`
- `0x18005bd49`

## callees

- `0x180005f2c`
- `0x180005fa4`
- `0x180022648`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002282b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002282b`

## pseudocode

```c
void __fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::~MidiEndpointMatchCriteria(
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *this)
{
  volatile signed __int32 *v1; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v5; // rdi
  int v6; // eax
  HANDLE v7; // rax
  volatile signed __int32 *v8; // rdi
  int v9; // eax
  HANDLE v10; // rax
  volatile signed __int32 *v11; // rdi
  int v12; // eax
  HANDLE v13; // rax
  volatile signed __int32 *v14; // rdi
  int v15; // eax
  HANDLE v16; // rax
  volatile signed __int32 *v17; // rdi
  int v18; // eax
  HANDLE v19; // rax
  volatile signed __int32 *v20; // rdi
  int v21; // eax
  HANDLE v22; // rax
  volatile signed __int32 *v23; // rdi
  int v24; // esi
  HANDLE v25; // rax

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 9);
  if ( v1 )
  {
    v3 = _InterlockedDecrement(v1 + 6);
    if ( v3 )
    {
      if ( v3 < 0 )
        goto LABEL_42;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    v6 = _InterlockedDecrement(v5 + 6);
    if ( v6 )
    {
      if ( v6 < 0 )
        goto LABEL_42;
    }
    else
    {
      v7 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v7, 0, (LPVOID)v5);
    }
    *((_QWORD *)this + 8) = 0;
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  if ( v8 )
  {
    v9 = _InterlockedDecrement(v8 + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        goto LABEL_42;
    }
    else
    {
      v10 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v10, 0, (LPVOID)v8);
    }
    *((_QWORD *)this + 6) = 0;
  }
  v11 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  if ( v11 )
  {
    v12 = _InterlockedDecrement(v11 + 6);
    if ( v12 )
    {
      if ( v12 < 0 )
        goto LABEL_42;
    }
    else
    {
      v13 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v13, 0, (LPVOID)v11);
    }
    *((_QWORD *)this + 5) = 0;
  }
  v14 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v14 )
  {
    v15 = _InterlockedDecrement(v14 + 6);
    if ( v15 )
    {
      if ( v15 < 0 )
        goto LABEL_42;
    }
    else
    {
      v16 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v16, 0, (LPVOID)v14);
    }
    *((_QWORD *)this + 4) = 0;
  }
  v17 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v17 )
  {
    v18 = _InterlockedDecrement(v17 + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        goto LABEL_42;
    }
    else
    {
      v19 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
    }
    *((_QWORD *)this + 3) = 0;
  }
  v20 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v20 )
  {
    v21 = _InterlockedDecrement(v20 + 6);
    if ( v21 )
    {
      if ( v21 < 0 )
        goto LABEL_42;
    }
    else
    {
      v22 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v22, 0, (LPVOID)v20);
    }
    *((_QWORD *)this + 1) = 0;
  }
  v23 = *(volatile signed __int32 **)this;
  if ( !*(_QWORD *)this )
    return;
  v24 = _InterlockedDecrement(v23 + 6);
  if ( v24 )
  {
    if ( v24 >= 0 )
      goto LABEL_39;
LABEL_42:
    abort();
  }
  v25 = WINRT_IMPL_GetProcessHeap();
  WINRT_IMPL_HeapFree(v25, 0, (LPVOID)v23);
LABEL_39:
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180022648  mov     [rsp+arg_0], rbx
0x18002264d  mov     [rsp+arg_8], rsi
0x180022652  push    rdi
0x180022653  sub     rsp, 20h
0x180022657  mov     rdi, [rcx+48h]
0x18002265b  or      esi, 0FFFFFFFFh
0x18002265e  mov     rbx, rcx
0x180022661  test    rdi, rdi
0x180022664  jz      short loc_180022697
0x180022666  mov     eax, esi
0x180022668  lock xadd [rdi+18h], eax
0x18002266d  sub     eax, 1
0x180022670  jnz     short loc_180022687
0x180022672  nop
0x180022673  call    WINRT_IMPL_GetProcessHeap
0x180022678  mov     rcx, rax; hHeap
0x18002267b  mov     r8, rdi; lpMem
0x18002267e  xor     edx, edx; dwFlags
0x180022680  call    WINRT_IMPL_HeapFree
0x180022685  jmp     short loc_18002268F
0x180022687  test    eax, eax
0x180022689  js      loc_18002282B
0x18002268f  mov     qword ptr [rbx+48h], 0
0x180022697  mov     rdi, [rbx+40h]
0x18002269b  test    rdi, rdi
0x18002269e  jz      short loc_1800226D1
0x1800226a0  mov     eax, esi
0x1800226a2  lock xadd [rdi+18h], eax
0x1800226a7  sub     eax, 1
0x1800226aa  jnz     short loc_1800226C1
0x1800226ac  nop
0x1800226ad  call    WINRT_IMPL_GetProcessHeap
0x1800226b2  mov     rcx, rax; hHeap
0x1800226b5  mov     r8, rdi; lpMem
0x1800226b8  xor     edx, edx; dwFlags
0x1800226ba  call    WINRT_IMPL_HeapFree
0x1800226bf  jmp     short loc_1800226C9
0x1800226c1  test    eax, eax
0x1800226c3  js      loc_18002282B
0x1800226c9  mov     qword ptr [rbx+40h], 0
0x1800226d1  mov     rdi, [rbx+30h]
0x1800226d5  test    rdi, rdi
0x1800226d8  jz      short loc_18002270B
0x1800226da  mov     eax, esi
0x1800226dc  lock xadd [rdi+18h], eax
0x1800226e1  sub     eax, 1
0x1800226e4  jnz     short loc_1800226FB
0x1800226e6  nop
0x1800226e7  call    WINRT_IMPL_GetProcessHeap
0x1800226ec  mov     rcx, rax; hHeap
0x1800226ef  mov     r8, rdi; lpMem
0x1800226f2  xor     edx, edx; dwFlags
0x1800226f4  call    WINRT_IMPL_HeapFree
0x1800226f9  jmp     short loc_180022703
0x1800226fb  test    eax, eax
0x1800226fd  js      loc_18002282B
0x180022703  mov     qword ptr [rbx+30h], 0
0x18002270b  mov     rdi, [rbx+28h]
0x18002270f  test    rdi, rdi
0x180022712  jz      short loc_180022745
0x180022714  mov     eax, esi
0x180022716  lock xadd [rdi+18h], eax
0x18002271b  sub     eax, 1
0x18002271e  jnz     short loc_180022735
0x180022720  nop
0x180022721  call    WINRT_IMPL_GetProcessHeap
0x180022726  mov     rcx, rax; hHeap
0x180022729  mov     r8, rdi; lpMem
0x18002272c  xor     edx, edx; dwFlags
0x18002272e  call    WINRT_IMPL_HeapFree
0x180022733  jmp     short loc_18002273D
0x180022735  test    eax, eax
0x180022737  js      loc_18002282B
0x18002273d  mov     qword ptr [rbx+28h], 0
0x180022745  mov     rdi, [rbx+20h]
0x180022749  test    rdi, rdi
0x18002274c  jz      short loc_18002277F
0x18002274e  mov     eax, esi
0x180022750  lock xadd [rdi+18h], eax
0x180022755  sub     eax, 1
0x180022758  jnz     short loc_18002276F
0x18002275a  nop
0x18002275b  call    WINRT_IMPL_GetProcessHeap
0x180022760  mov     rcx, rax; hHeap
0x180022763  mov     r8, rdi; lpMem
0x180022766  xor     edx, edx; dwFlags
0x180022768  call    WINRT_IMPL_HeapFree
0x18002276d  jmp     short loc_180022777
0x18002276f  test    eax, eax
0x180022771  js      loc_18002282B
0x180022777  mov     qword ptr [rbx+20h], 0
0x18002277f  mov     rdi, [rbx+18h]
0x180022783  test    rdi, rdi
0x180022786  jz      short loc_1800227B5
0x180022788  mov     eax, esi
0x18002278a  lock xadd [rdi+18h], eax
0x18002278f  sub     eax, 1
0x180022792  jnz     short loc_1800227A9
0x180022794  nop
0x180022795  call    WINRT_IMPL_GetProcessHeap
0x18002279a  mov     rcx, rax; hHeap
0x18002279d  mov     r8, rdi; lpMem
0x1800227a0  xor     edx, edx; dwFlags
0x1800227a2  call    WINRT_IMPL_HeapFree
0x1800227a7  jmp     short loc_1800227AD
0x1800227a9  test    eax, eax
0x1800227ab  js      short loc_18002282B
0x1800227ad  mov     qword ptr [rbx+18h], 0
0x1800227b5  mov     rdi, [rbx+8]
0x1800227b9  test    rdi, rdi
0x1800227bc  jz      short loc_1800227EB
0x1800227be  mov     eax, esi
0x1800227c0  lock xadd [rdi+18h], eax
0x1800227c5  sub     eax, 1
0x1800227c8  jnz     short loc_1800227DF
0x1800227ca  nop
0x1800227cb  call    WINRT_IMPL_GetProcessHeap
0x1800227d0  mov     rcx, rax; hHeap
0x1800227d3  mov     r8, rdi; lpMem
0x1800227d6  xor     edx, edx; dwFlags
0x1800227d8  call    WINRT_IMPL_HeapFree
0x1800227dd  jmp     short loc_1800227E3
0x1800227df  test    eax, eax
0x1800227e1  js      short loc_18002282B
0x1800227e3  mov     qword ptr [rbx+8], 0
0x1800227eb  mov     rdi, [rbx]
0x1800227ee  test    rdi, rdi
0x1800227f1  jz      short loc_180022817
0x1800227f3  lock xadd [rdi+18h], esi
0x1800227f8  sub     esi, 1
0x1800227fb  jnz     short loc_180022827
0x1800227fd  nop
0x1800227fe  call    WINRT_IMPL_GetProcessHeap
0x180022803  mov     rcx, rax; hHeap
0x180022806  mov     r8, rdi; lpMem
0x180022809  xor     edx, edx; dwFlags
0x18002280b  call    WINRT_IMPL_HeapFree
0x180022810  mov     qword ptr [rbx], 0
0x180022817  mov     rbx, [rsp+28h+arg_0]
0x18002281c  mov     rsi, [rsp+28h+arg_8]
0x180022821  add     rsp, 20h
0x180022825  pop     rdi
0x180022826  retn
0x180022827  test    esi, esi
0x180022829  jns     short loc_180022810
0x18002282b  call    cs:__imp_abort
```
