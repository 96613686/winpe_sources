# _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800070c0`
- end: `0x18000733d`
- name: `?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `637`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, RTL_SRWLOCK *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x180003118`
- `0x1800070c0`
- `0x180008a80`
- `0x18000941c`
- `0x180009830`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007172`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007172`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007189`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007189`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007109`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007109`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007303`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007303`

## string_xrefs

- `0x18000716b`: `ntdll.dll`

## pseudocode

```c
void __fastcall _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rsi
  int updated; // r14d
  int v6; // r15d
  HMODULE ModuleHandleW; // rax
  int v8; // edi
  unsigned int v9; // r9d
  char *Ptr; // r8
  int v11; // r10d
  char *v12; // r14
  _DWORD *v13; // rdx
  _DWORD *v14; // rcx
  unsigned int v15; // [rsp+40h] [rbp-C0h]
  int v16[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v17[1024]; // [rsp+50h] [rbp-B0h] BYREF

  if ( LOBYTE(Context->Ptr) )
  {
    v4 = Context + 5;
    AcquireSRWLockExclusive(Context + 5);
    if ( (PVOID)((char *)Context[30].Ptr - (char *)Context[29].Ptr) >= (PVOID)0xC )
    {
      updated = 0;
      v6 = 0;
      do
      {
        memset_0(v17, 0, sizeof(v17));
        v16[0] = 0;
        if ( g_wil_details_pfnNtQueryWnfStateData )
          goto LABEL_9;
        ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
        if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
        {
          ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
          `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
        }
        g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
        if ( g_wil_details_pfnNtQueryWnfStateData )
        {
LABEL_9:
          v8 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, int *))g_wil_details_pfnNtQueryWnfStateData)(
                 &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                 0,
                 0,
                 v16);
          if ( !v8 )
          {
            v9 = 0;
            v15 = 0;
            Ptr = (char *)Context[29].Ptr;
            v11 = 0;
            v12 = &Ptr[12 * (((char *)Context[30].Ptr - (char *)Ptr) / 0xCuLL)];
            while ( Ptr != v12 )
            {
              v13 = &v17[3 * v11];
              if ( v17 == v13 )
              {
LABEL_16:
                if ( (unsigned __int64)v9 + 12 <= 0x1000 )
                {
                  v9 += 12;
                  *(_QWORD *)v13 = *(_QWORD *)Ptr;
                  ++v11;
                  v13[2] = *((_DWORD *)Ptr + 2);
                  v15 = v9;
                }
              }
              else
              {
                v14 = v17;
                while ( *v14 != *(_DWORD *)Ptr || *((_WORD *)v14 + 2) != *((_WORD *)Ptr + 2) )
                {
                  v14 += 3;
                  if ( v14 == v13 )
                    goto LABEL_16;
                }
                v14[2] += *((_DWORD *)Ptr + 2);
                v9 = v15;
              }
              Ptr += 12;
            }
            updated = wil_details_NtUpdateWnfStateData(
                        (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                        (unsigned int)v17,
                        v9,
                        v9,
                        (unsigned int)v17,
                        v16[0],
                        1);
          }
        }
        else
        {
          v8 = -1073741511;
        }
        if ( updated != -1073741823 )
          break;
        if ( ++v6 >= 100 )
          break;
      }
      while ( !v8 );
      v4 = Context + 5;
      Context[30].Ptr = Context[29].Ptr;
    }
    LOBYTE(Context[8].Ptr) = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
}

```

## disassembly

```asm
0x1800070c0  push    rbp
0x1800070c2  push    rbx
0x1800070c3  push    rsi
0x1800070c4  push    rdi
0x1800070c5  push    r12
0x1800070c7  push    r13
0x1800070c9  push    r14
0x1800070cb  push    r15
0x1800070cd  lea     rbp, [rsp-0F68h]
0x1800070d5  mov     eax, 1068h
0x1800070da  call    _alloca_probe
0x1800070df  sub     rsp, rax
0x1800070e2  mov     rax, cs:__security_cookie
0x1800070e9  xor     rax, rsp
0x1800070ec  mov     [rbp+0FA0h+var_50], rax
0x1800070f3  xor     r12d, r12d
0x1800070f6  mov     rbx, rdx
0x1800070f9  cmp     [rdx], r12b
0x1800070fc  jz      loc_180007309
0x180007102  lea     rsi, [rdx+28h]
0x180007106  mov     rcx, rsi; SRWLock
0x180007109  call    cs:__imp_AcquireSRWLockExclusive
0x18000710f  mov     rax, [rbx+0F0h]
0x180007116  sub     rax, [rbx+0E8h]
0x18000711d  cmp     rax, 0Ch
0x180007121  jb      loc_1800072F7
0x180007127  mov     r14d, r12d
0x18000712a  mov     r15d, r12d
0x18000712d  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180007137  mov     r13d, 1000h
0x18000713d  mov     r8, r13; Size
0x180007140  lea     rcx, [rsp+10A0h+var_1050]; void *
0x180007145  xor     edx, edx; Val
0x180007147  call    memset_0
0x18000714c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, r12
0x180007153  mov     [rsp+10A0h+var_1060], r13d
0x180007158  mov     [rsp+10A0h+var_105C], r12d
0x18000715d  jnz     short loc_1800071A5
0x18000715f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007166  test    rax, rax
0x180007169  jnz     short loc_18000717F
0x18000716b  lea     rcx, ModuleName; "ntdll.dll"
0x180007172  call    cs:__imp_GetModuleHandleW
0x180007178  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000717f  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180007186  mov     rcx, rax; hModule
0x180007189  call    cs:__imp_GetProcAddress
0x18000718f  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180007196  test    rax, rax
0x180007199  jnz     short loc_1800071A5
0x18000719b  mov     edi, 0C0000139h
0x1800071a0  jmp     loc_1800072CB
0x1800071a5  lea     rax, [rsp+10A0h+var_1060]
0x1800071aa  xor     r8d, r8d
0x1800071ad  mov     [rsp+10A0h+var_1078], rax
0x1800071b2  lea     r9, [rsp+10A0h+var_105C]
0x1800071b7  lea     rax, [rsp+10A0h+var_1050]
0x1800071bc  xor     edx, edx
0x1800071be  mov     [rsp+10A0h+var_1080], rax
0x1800071c3  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800071ca  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800071d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071d6  mov     edi, eax
0x1800071d8  test    eax, eax
0x1800071da  jnz     loc_1800072CB
0x1800071e0  mov     r9d, [rsp+10A0h+var_1060]
0x1800071e5  mov     rax, rsi
0x1800071e8  mul     r9
0x1800071eb  shr     rdx, 3
0x1800071ef  lea     rcx, [rdx+rdx*2]
0x1800071f3  shl     rcx, 2
0x1800071f7  cmp     r9, rcx
0x1800071fa  jz      short loc_180007204
0x1800071fc  mov     r9d, r12d
0x1800071ff  mov     [rsp+10A0h+var_1060], r12d
0x180007204  mov     r8, [rbx+0E8h]
0x18000720b  mov     rax, rsi
0x18000720e  mov     ecx, r9d
0x180007211  mul     rcx
0x180007214  mov     rcx, [rbx+0F0h]
0x18000721b  mov     rax, rsi
0x18000721e  mov     r10, rdx
0x180007221  sub     rcx, r8
0x180007224  mul     rcx
0x180007227  shr     r10, 3
0x18000722b  shr     rdx, 3
0x18000722f  lea     rax, [rdx+rdx*2]
0x180007233  lea     r14, [r8+rax*4]
0x180007237  jmp     short loc_18000729F
0x180007239  mov     eax, r10d
0x18000723c  lea     rcx, [rax+rax*2]
0x180007240  lea     rdx, [rdx+rcx*4]
0x180007244  lea     rax, [rsp+10A0h+var_1050]
0x180007249  cmp     rax, rdx
0x18000724c  jz      short loc_180007273
0x18000724e  mov     r11d, [r8]
0x180007251  lea     rcx, [rsp+10A0h+var_1050]
0x180007256  cmp     [rcx], r11d
0x180007259  jnz     short loc_18000726A
0x18000725b  movzx   eax, word ptr [r8+4]
0x180007260  cmp     [rcx+4], ax
0x180007264  jz      loc_18000732C
0x18000726a  add     rcx, 0Ch
0x18000726e  cmp     rcx, rdx
0x180007271  jnz     short loc_180007256
0x180007273  mov     eax, r9d
0x180007276  add     rax, 0Ch
0x18000727a  cmp     rax, r13
0x18000727d  ja      short loc_18000729B
0x18000727f  movsd   xmm0, qword ptr [r8]
0x180007284  add     r9d, 0Ch
0x180007288  movsd   qword ptr [rdx], xmm0
0x18000728c  inc     r10d
0x18000728f  mov     eax, [r8+8]
0x180007293  mov     [rdx+8], eax
0x180007296  mov     [rsp+10A0h+var_1060], r9d
0x18000729b  add     r8, 0Ch
0x18000729f  lea     rdx, [rsp+10A0h+var_1050]
0x1800072a4  cmp     r8, r14
0x1800072a7  jnz     short loc_180007239
0x1800072a9  mov     eax, [rsp+10A0h+var_105C]
0x1800072ad  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800072b4  mov     [rsp+10A0h+var_1070], 1
0x1800072bc  mov     r8d, r9d
0x1800072bf  mov     dword ptr [rsp+10A0h+var_1078], eax
0x1800072c3  call    wil_details_NtUpdateWnfStateData
0x1800072c8  mov     r14d, eax
0x1800072cb  cmp     r14d, 0C0000001h
0x1800072d2  jnz     short loc_1800072E5
0x1800072d4  inc     r15d
0x1800072d7  cmp     r15d, 64h ; 'd'
0x1800072db  jge     short loc_1800072E5
0x1800072dd  test    edi, edi
0x1800072df  jz      loc_18000713D
0x1800072e5  mov     rax, [rbx+0E8h]
0x1800072ec  lea     rsi, [rbx+28h]
0x1800072f0  mov     [rbx+0F0h], rax
0x1800072f7  mov     [rbx+40h], r12b
0x1800072fb  test    rsi, rsi
0x1800072fe  jz      short loc_180007309
0x180007300  mov     rcx, rsi; SRWLock
0x180007303  call    cs:__imp_ReleaseSRWLockExclusive
0x180007309  mov     rcx, [rbp+0FA0h+var_50]
0x180007310  xor     rcx, rsp; StackCookie
0x180007313  call    __security_check_cookie
0x180007318  add     rsp, 1068h
0x18000731f  pop     r15
0x180007321  pop     r14
0x180007323  pop     r13
0x180007325  pop     r12
0x180007327  pop     rdi
0x180007328  pop     rsi
0x180007329  pop     rbx
0x18000732a  pop     rbp
0x18000732b  retn
0x18000732c  mov     eax, [r8+8]
0x180007330  add     [rcx+8], eax
0x180007333  mov     r9d, [rsp+10A0h+var_1060]
0x180007338  jmp     loc_18000729B
```
