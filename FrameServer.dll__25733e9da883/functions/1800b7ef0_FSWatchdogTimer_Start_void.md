# FSWatchdogTimer::Start(void)

- ea: `0x1800b7ef0`
- end: `0x1800b8083`
- name: `?Start@FSWatchdogTimer@@UEAAJXZ`
- size: `403`
- prototype: `__int64 __fastcall(FSWatchdogTimer *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180009608`
- `0x18001807c`
- `0x1800b7ef0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b806b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b806b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b7f06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b7f06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7fc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7fc3`
- `MFPlat!MFGetSystemTime` at `0x1800b7fa1`
- `MFPlat!MFGetSystemTime` at `0x1800b7fa1`

## pseudocode

```c
__int64 __fastcall FSWatchdogTimer::Start(FSWatchdogTimer *this)
{
  _QWORD *v2; // rdi
  unsigned int v3; // edi
  __int64 v4; // rdx
  MFTIME v5; // rax
  bool v6; // zf
  DWORD CurrentThreadId; // eax
  __int64 v8; // rcx
  __int64 v9; // xmm1_8
  void (__fastcall *v10)(__int64, __int128 *); // rax
  __int128 v12; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-18h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = (_QWORD *)((char *)this + 1880);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 25, &WPP_79730b659bd239cbae37bb359f886a1d_Traceguids, this, *v2);
  if ( *((_DWORD *)this + 462) == 2 )
  {
    v3 = -1072875854;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_79730b659bd239cbae37bb359f886a1d_Traceguids,
        this,
        -1072875854);
    if ( byte_18010EC4D )
    {
      v4 = 27;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v4, &WPP_79730b659bd239cbae37bb359f886a1d_Traceguids, this, v3);
    }
  }
  else
  {
    *((_DWORD *)this + 462) = 2;
    v5 = MFGetSystemTime();
    v6 = *((_QWORD *)this + 242) == 0;
    *((_QWORD *)this + 232) = v5;
    *((_QWORD *)this + 233) = 0;
    if ( !v6 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 242);
      *((_DWORD *)this + 486) = CurrentThreadId;
      *((_DWORD *)this + 487) = -1;
      *((_QWORD *)this + 244) = this;
      *((_DWORD *)this + 490) = 0;
      v9 = *((_QWORD *)this + 245);
      v10 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v8 + 24LL);
      v12 = *(_OWORD *)((char *)this + 1944);
      v13 = v9;
      v10(v8, &v12);
    }
    (*(void (__fastcall **)(char *, _QWORD, _QWORD))(*((_QWORD *)this + 7) + 48LL))(
      (char *)this + 56,
      *((unsigned int *)this + 482),
      -*v2);
    v3 = 0;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v4 = 28;
      goto LABEL_12;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v3;
}

```

## disassembly

```asm
0x1800b7ef0  mov     [rsp+arg_0], rbx
0x1800b7ef5  mov     [rsp+arg_8], rsi
0x1800b7efa  push    rdi
0x1800b7efb  sub     rsp, 50h
0x1800b7eff  mov     rbx, rcx
0x1800b7f02  add     rcx, 10h; lpCriticalSection
0x1800b7f06  call    cs:__imp_EnterCriticalSection
0x1800b7f0c  cmp     cs:byte_18010EC4D, 8
0x1800b7f13  lea     rdi, [rbx+758h]
0x1800b7f1a  jb      short loc_1800B7F46
0x1800b7f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7f23  lea     r8, WPP_79730b659bd239cbae37bb359f886a1d_Traceguids
0x1800b7f2a  mov     rax, [rdi]
0x1800b7f2d  mov     edx, 19h
0x1800b7f32  mov     r9, rbx
0x1800b7f35  mov     [rsp+58h+var_38], rax
0x1800b7f3a  mov     rcx, [rcx+0D8h]
0x1800b7f41  call    WPP_SF_qq
0x1800b7f46  cmp     dword ptr [rbx+738h], 2
0x1800b7f4d  jnz     short loc_1800B7F97
0x1800b7f4f  mov     edi, 0C00D36B2h
0x1800b7f54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7f5b  jb      short loc_1800B7F80
0x1800b7f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7f64  lea     r8, WPP_79730b659bd239cbae37bb359f886a1d_Traceguids
0x1800b7f6b  mov     edx, 1Ah
0x1800b7f70  mov     dword ptr [rsp+58h+var_38], edi
0x1800b7f74  mov     r9, rbx
0x1800b7f77  mov     rcx, [rcx+10h]
0x1800b7f7b  call    WPP_SF_qD
0x1800b7f80  cmp     cs:byte_18010EC4D, 1
0x1800b7f87  jb      loc_1800B8067
0x1800b7f8d  mov     edx, 1Bh
0x1800b7f92  jmp     loc_1800B8046
0x1800b7f97  mov     dword ptr [rbx+738h], 2
0x1800b7fa1  call    cs:__imp_MFGetSystemTime
0x1800b7fa7  cmp     qword ptr [rbx+790h], 0
0x1800b7faf  mov     [rbx+740h], rax
0x1800b7fb6  mov     qword ptr [rbx+748h], 0
0x1800b7fc1  jz      short loc_1800B801C
0x1800b7fc3  call    cs:__imp_GetCurrentThreadId
0x1800b7fc9  mov     rcx, [rbx+790h]
0x1800b7fd0  lea     rdx, [rsp+58h+var_28]
0x1800b7fd5  mov     [rbx+798h], eax
0x1800b7fdb  mov     dword ptr [rbx+79Ch], 0FFFFFFFFh
0x1800b7fe5  mov     [rbx+7A0h], rbx
0x1800b7fec  mov     dword ptr [rbx+7A8h], 0
0x1800b7ff6  mov     rax, [rcx]
0x1800b7ff9  movups  xmm0, xmmword ptr [rbx+798h]
0x1800b8000  movsd   xmm1, qword ptr [rbx+7A8h]
0x1800b8008  mov     rax, [rax+18h]
0x1800b800c  movaps  [rsp+58h+var_28], xmm0
0x1800b8011  movsd   [rsp+58h+var_18], xmm1
0x1800b8017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b801c  mov     r8, [rdi]
0x1800b801f  lea     rcx, [rbx+38h]
0x1800b8023  mov     rax, [rcx]
0x1800b8026  neg     r8
0x1800b8029  mov     edx, [rbx+788h]
0x1800b802f  mov     rax, [rax+30h]
0x1800b8033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8038  xor     edi, edi
0x1800b803a  cmp     cs:byte_18010EC4D, 8
0x1800b8041  jb      short loc_1800B8067
0x1800b8043  lea     edx, [rdi+1Ch]
0x1800b8046  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b804d  lea     r8, WPP_79730b659bd239cbae37bb359f886a1d_Traceguids
0x1800b8054  mov     r9, rbx
0x1800b8057  mov     dword ptr [rsp+58h+var_38], edi
0x1800b805b  mov     rcx, [rcx+0D8h]
0x1800b8062  call    WPP_SF_qD
0x1800b8067  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800b806b  call    cs:__imp_LeaveCriticalSection
0x1800b8071  mov     rbx, [rsp+58h+arg_0]
0x1800b8076  mov     eax, edi
0x1800b8078  mov     rsi, [rsp+58h+arg_8]
0x1800b807d  add     rsp, 50h
0x1800b8081  pop     rdi
0x1800b8082  retn
```
