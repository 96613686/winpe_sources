# OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(void *,ushort const *,ushort const *,int,ushort const *,ushort const *,ushort * *)

- ea: `0x18001ef10`
- end: `0x18001f347`
- name: `?PerformCommonClientDownload@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAXPEBG1H11PEAPEAG@Z`
- size: `1079`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(const wchar_t *, __int64 *), void *, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ae7c`

## callees

- `0x18001ec50`
- `0x18001ef10`
- `0x180022f34`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f19d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f2c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f19d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f2c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f18c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f2af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f18c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f2af`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(
        __int64 (__fastcall **this)(const wchar_t *, __int64 *),
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        unsigned __int16 **a8)
{
  unsigned __int16 **v8; // r15
  int v13; // ebx
  const unsigned __int16 *v14; // rsi
  __int64 v15; // rax
  unsigned __int64 v16; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rsi
  HANDLE v21; // rax
  unsigned __int16 *v22; // rax
  int v24; // [rsp+40h] [rbp-41h] BYREF
  int v25; // [rsp+44h] [rbp-3Dh] BYREF
  const wchar_t *v26; // [rsp+48h] [rbp-39h] BYREF
  __int64 v27; // [rsp+50h] [rbp-31h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp-21h] BYREF
  __int64 v30; // [rsp+68h] [rbp-19h] BYREF
  char *v31; // [rsp+70h] [rbp-11h] BYREF
  int v32; // [rsp+D0h] [rbp+4Fh] BYREF

  v8 = a8;
  v30 = 0;
  v26 = 0;
  v27 = 0;
  v32 = 0;
  v24 = 0;
  v25 = 0;
  v28 = 0;
  v31 = 0;
  v29 = 0;
  if ( a8 )
    *a8 = 0;
  v13 = this[231](L"OSQ", &v30);
  if ( v13 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(const wchar_t **))this[221])(&v26);
    if ( v13 >= 0 )
    {
      if ( !a5
        || (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, __int64))this[223])(v26, 1, 1), v13 >= 0)
        && (v13 = this[223](v26, (__int64 *)2), v13 >= 0) )
      {
        if ( !a2 || (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, void *))this[226])(v26, 1, a2), v13 >= 0) )
        {
          if ( !a3
            || (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, const unsigned __int16 *))this[225])(
                        v26,
                        1,
                        a3),
                v13 >= 0) )
          {
            if ( !a4
              || (v13 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const unsigned __int16 *))this[225])(
                          v26,
                          0,
                          a4),
                  v13 >= 0) )
            {
              v14 = a6;
              if ( !a6
                || (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, __int64))this[224])(v26, 1, 1), v13 >= 0)
                && (v13 = ((__int64 (__fastcall *)(const wchar_t *, __int64, const unsigned __int16 *))this[225])(
                            v26,
                            3,
                            v14),
                    v13 >= 0) )
              {
                if ( !a7 || (v13 = this[225](v26, (__int64 *)4), v13 >= 0) )
                {
                  v13 = ((__int64 (__fastcall *)(__int64, char *, char *, const wchar_t *, const wchar_t *, __int64 *))this[233])(
                          v30,
                          (char *)this + 40,
                          (char *)this + 560,
                          L"v2.0",
                          v26,
                          &v27);
                  if ( v13 >= 0 )
                  {
                    v13 = ((__int64 (__fastcall *)(__int64, _QWORD, int *))this[228])(v27, 0, &v32);
                    if ( v13 >= 0 )
                    {
                      switch ( v32 )
                      {
                        case 200:
                          v13 = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int16 **))this[230])(v27, 0, &v28);
                          if ( v13 < 0 )
                            break;
                          v15 = -1;
                          do
                            ++v15;
                          while ( v28[v15] );
                          v16 = (unsigned int)(v15 + 1);
                          ProcessHeap = GetProcessHeap();
                          v18 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v16);
                          this[4] = (__int64 (__fastcall *)(const wchar_t *, __int64 *))v18;
                          if ( !v18 )
                            goto LABEL_26;
                          v13 = StringCchCopyW(v18, v16, v28);
                          if ( v13 >= 0 )
                          {
                            v13 = ((__int64 (__fastcall *)(__int64, _QWORD, char **))this[229])(v27, 0, &v31);
                            if ( v13 >= 0 )
                              v13 = OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(
                                      (OneCore::Base::Telemetry::OneSettingsQuery *)this,
                                      v31);
                          }
                          break;
                        case 304:
                          v13 = 1;
                          break;
                        case 407:
                          v13 = ((__int64 (__fastcall *)(__int64, __int64, int *))this[228])(v27, 2, &v24);
                          if ( v13 < 0 )
                            break;
                          v13 = ((__int64 (__fastcall *)(__int64, __int64, int *))this[228])(v27, 4, &v25);
                          if ( v13 < 0 )
                            break;
                          if ( !v8 || (v24 & 1) == 0 || v25 != 1 )
                          {
LABEL_44:
                            v13 = -2147467259;
                            break;
                          }
                          v13 = ((__int64 (__fastcall *)(__int64, __int64, unsigned __int16 **))this[230])(v27, 3, &v29);
                          if ( v13 >= 0 )
                          {
                            v19 = -1;
                            do
                              ++v19;
                            while ( v29[v19] );
                            v20 = (unsigned int)(v19 + 1);
                            v21 = GetProcessHeap();
                            v22 = (unsigned __int16 *)HeapAlloc(v21, 8u, 2 * v20);
                            *v8 = v22;
                            if ( !v22 )
                            {
LABEL_26:
                              v13 = -2147024882;
                              break;
                            }
                            v13 = StringCchCopyW(v22, (unsigned int)v20, v29);
                            if ( v13 >= 0 )
                              v13 = -2147024891;
                          }
                          break;
                        default:
                          goto LABEL_44;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v27 )
    ((void (*)(void))this[227])();
  if ( v26 )
    ((void (*)(void))this[222])();
  if ( v30 )
    ((void (*)(void))this[232])();
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001ef10  push    rbp
0x18001ef12  push    rbx
0x18001ef13  push    rsi
0x18001ef14  push    rdi
0x18001ef15  push    r12
0x18001ef17  push    r13
0x18001ef19  push    r14
0x18001ef1b  push    r15
0x18001ef1d  lea     rbp, [rsp-7]
0x18001ef22  sub     rsp, 88h
0x18001ef29  mov     r15, [rbp+3Fh+arg_38]
0x18001ef30  xor     r13d, r13d
0x18001ef33  mov     [rbp+3Fh+var_58], r13
0x18001ef37  mov     r12, r9
0x18001ef3a  mov     [rbp+3Fh+var_78], r13
0x18001ef3e  mov     r14, r8
0x18001ef41  mov     [rbp+3Fh+var_70], r13
0x18001ef45  mov     rsi, rdx
0x18001ef48  mov     [rbp+3Fh+arg_0], r13d
0x18001ef4c  mov     rdi, rcx
0x18001ef4f  mov     [rbp+3Fh+var_80], r13d
0x18001ef53  mov     [rbp+3Fh+var_7C], r13d
0x18001ef57  mov     [rbp+3Fh+var_68], r13
0x18001ef5b  mov     [rbp+3Fh+var_50], r13
0x18001ef5f  mov     [rbp+3Fh+var_60], r13
0x18001ef63  test    r15, r15
0x18001ef66  jz      short loc_18001EF6B
0x18001ef68  mov     [r15], r13
0x18001ef6b  mov     rax, [rdi+738h]
0x18001ef72  lea     rdx, [rbp+3Fh+var_58]
0x18001ef76  lea     rcx, aOsq; "OSQ"
0x18001ef7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef82  mov     ebx, eax
0x18001ef84  test    eax, eax
0x18001ef86  js      loc_18001F2F2
0x18001ef8c  mov     rax, [rdi+6E8h]
0x18001ef93  lea     rcx, [rbp+3Fh+var_78]
0x18001ef97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef9c  mov     ebx, eax
0x18001ef9e  test    eax, eax
0x18001efa0  js      loc_18001F2F2
0x18001efa6  cmp     [rbp+3Fh+arg_20], r13d
0x18001efaa  jz      short loc_18001EFEF
0x18001efac  mov     rcx, [rbp+3Fh+var_78]
0x18001efb0  mov     edx, 1
0x18001efb5  mov     rax, [rdi+6F8h]
0x18001efbc  mov     r8d, edx
0x18001efbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efc4  mov     ebx, eax
0x18001efc6  test    eax, eax
0x18001efc8  js      loc_18001F2F2
0x18001efce  mov     rcx, [rbp+3Fh+var_78]
0x18001efd2  xor     r8d, r8d
0x18001efd5  mov     rax, [rdi+6F8h]
0x18001efdc  lea     edx, [r8+2]
0x18001efe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efe5  mov     ebx, eax
0x18001efe7  test    eax, eax
0x18001efe9  js      loc_18001F2F2
0x18001efef  test    rsi, rsi
0x18001eff2  jz      short loc_18001F016
0x18001eff4  mov     rcx, [rbp+3Fh+var_78]
0x18001eff8  mov     r8, rsi
0x18001effb  mov     rax, [rdi+710h]
0x18001f002  mov     edx, 1
0x18001f007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f00c  mov     ebx, eax
0x18001f00e  test    eax, eax
0x18001f010  js      loc_18001F2F2
0x18001f016  test    r14, r14
0x18001f019  jz      short loc_18001F043
0x18001f01b  mov     rcx, [rbp+3Fh+var_78]
0x18001f01f  mov     r8, r14
0x18001f022  mov     rax, [rdi+708h]
0x18001f029  mov     r14d, 1
0x18001f02f  mov     edx, r14d
0x18001f032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f037  mov     ebx, eax
0x18001f039  test    eax, eax
0x18001f03b  js      loc_18001F2F2
0x18001f041  jmp     short loc_18001F049
0x18001f043  mov     r14d, 1
0x18001f049  test    r12, r12
0x18001f04c  jz      short loc_18001F06D
0x18001f04e  mov     rcx, [rbp+3Fh+var_78]
0x18001f052  mov     r8, r12
0x18001f055  mov     rax, [rdi+708h]
0x18001f05c  xor     edx, edx
0x18001f05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f063  mov     ebx, eax
0x18001f065  test    eax, eax
0x18001f067  js      loc_18001F2F2
0x18001f06d  mov     rsi, [rbp+3Fh+arg_28]
0x18001f071  mov     r12d, 3
0x18001f077  test    rsi, rsi
0x18001f07a  jz      short loc_18001F0BC
0x18001f07c  mov     rcx, [rbp+3Fh+var_78]
0x18001f080  mov     r8d, r14d
0x18001f083  mov     rax, [rdi+700h]
0x18001f08a  mov     edx, r14d
0x18001f08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f092  mov     ebx, eax
0x18001f094  test    eax, eax
0x18001f096  js      loc_18001F2F2
0x18001f09c  mov     rcx, [rbp+3Fh+var_78]
0x18001f0a0  mov     r8, rsi
0x18001f0a3  mov     rax, [rdi+708h]
0x18001f0aa  mov     edx, r12d
0x18001f0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b2  mov     ebx, eax
0x18001f0b4  test    eax, eax
0x18001f0b6  js      loc_18001F2F2
0x18001f0bc  mov     r8, [rbp+3Fh+arg_30]
0x18001f0c0  mov     esi, 4
0x18001f0c5  test    r8, r8
0x18001f0c8  jz      short loc_18001F0E6
0x18001f0ca  mov     rcx, [rbp+3Fh+var_78]
0x18001f0ce  mov     edx, esi
0x18001f0d0  mov     rax, [rdi+708h]
0x18001f0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0dc  mov     ebx, eax
0x18001f0de  test    eax, eax
0x18001f0e0  js      loc_18001F2F2
0x18001f0e6  mov     rcx, [rbp+3Fh+var_78]
0x18001f0ea  lea     rax, [rbp+3Fh+var_70]
0x18001f0ee  mov     [rsp+0C0h+var_98], rax
0x18001f0f3  lea     r8, [rdi+230h]
0x18001f0fa  mov     rax, [rdi+748h]
0x18001f101  lea     rdx, [rdi+28h]
0x18001f105  mov     [rsp+0C0h+var_A0], rcx
0x18001f10a  lea     r9, aV20; "v2.0"
0x18001f111  mov     rcx, [rbp+3Fh+var_58]
0x18001f115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f11a  mov     ebx, eax
0x18001f11c  test    eax, eax
0x18001f11e  js      loc_18001F2F2
0x18001f124  mov     rcx, [rbp+3Fh+var_70]
0x18001f128  lea     r8, [rbp+3Fh+arg_0]
0x18001f12c  mov     rax, [rdi+720h]
0x18001f133  xor     edx, edx
0x18001f135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f13a  mov     ebx, eax
0x18001f13c  test    eax, eax
0x18001f13e  js      loc_18001F2F2
0x18001f144  mov     eax, [rbp+3Fh+arg_0]
0x18001f147  cmp     eax, 0C8h
0x18001f14c  jnz     loc_18001F202
0x18001f152  mov     rcx, [rbp+3Fh+var_70]
0x18001f156  lea     r8, [rbp+3Fh+var_68]
0x18001f15a  mov     rax, [rdi+730h]
0x18001f161  xor     edx, edx
0x18001f163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f168  mov     ebx, eax
0x18001f16a  test    eax, eax
0x18001f16c  js      loc_18001F2F2
0x18001f172  mov     rcx, [rbp+3Fh+var_68]
0x18001f176  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f17a  inc     rax
0x18001f17d  cmp     [rcx+rax*2], r13w
0x18001f182  jnz     short loc_18001F17A
0x18001f184  inc     eax
0x18001f186  mov     esi, eax
0x18001f188  lea     rbx, [rax+rax]
0x18001f18c  call    cs:__imp_GetProcessHeap
0x18001f192  mov     r8, rbx; dwBytes
0x18001f195  mov     edx, 8; dwFlags
0x18001f19a  mov     rcx, rax; hHeap
0x18001f19d  call    cs:__imp_HeapAlloc
0x18001f1a3  mov     [rdi+20h], rax
0x18001f1a7  test    rax, rax
0x18001f1aa  jnz     short loc_18001F1B6
0x18001f1ac  mov     ebx, 8007000Eh
0x18001f1b1  jmp     loc_18001F2F2
0x18001f1b6  mov     r8, [rbp+3Fh+var_68]; unsigned __int16 *
0x18001f1ba  mov     rdx, rsi; unsigned __int64
0x18001f1bd  mov     rcx, rax; unsigned __int16 *
0x18001f1c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f1c5  mov     ebx, eax
0x18001f1c7  test    eax, eax
0x18001f1c9  js      loc_18001F2F2
0x18001f1cf  mov     rcx, [rbp+3Fh+var_70]
0x18001f1d3  lea     r8, [rbp+3Fh+var_50]
0x18001f1d7  mov     rax, [rdi+728h]
0x18001f1de  xor     edx, edx
0x18001f1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1e5  mov     ebx, eax
0x18001f1e7  test    eax, eax
0x18001f1e9  js      loc_18001F2F2
0x18001f1ef  mov     rdx, [rbp+3Fh+var_50]; char *
0x18001f1f3  mov     rcx, rdi; this
0x18001f1f6  call    ?ParseJsonResult@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAD@Z; OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(char *)
0x18001f1fb  mov     ebx, eax
0x18001f1fd  jmp     loc_18001F2F2
0x18001f202  cmp     eax, 130h
0x18001f207  jnz     short loc_18001F211
0x18001f209  mov     ebx, r14d
0x18001f20c  jmp     loc_18001F2F2
0x18001f211  cmp     eax, 197h
0x18001f216  jnz     loc_18001F2ED
0x18001f21c  mov     rcx, [rbp+3Fh+var_70]
0x18001f220  lea     r8, [rbp+3Fh+var_80]
0x18001f224  mov     rax, [rdi+720h]
0x18001f22b  mov     edx, 2
0x18001f230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f235  mov     ebx, eax
0x18001f237  test    eax, eax
0x18001f239  js      loc_18001F2F2
0x18001f23f  mov     rcx, [rbp+3Fh+var_70]
0x18001f243  lea     r8, [rbp+3Fh+var_7C]
0x18001f247  mov     rax, [rdi+720h]
0x18001f24e  mov     edx, esi
0x18001f250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f255  mov     ebx, eax
0x18001f257  test    eax, eax
0x18001f259  js      loc_18001F2F2
0x18001f25f  test    r15, r15
0x18001f262  jz      loc_18001F2ED
0x18001f268  mov     eax, [rbp+3Fh+var_80]
0x18001f26b  and     eax, r14d
0x18001f26e  test    al, al
0x18001f270  jz      short loc_18001F2ED
0x18001f272  cmp     [rbp+3Fh+var_7C], r14d
0x18001f276  jnz     short loc_18001F2ED
0x18001f278  mov     rcx, [rbp+3Fh+var_70]
0x18001f27c  lea     r8, [rbp+3Fh+var_60]
0x18001f280  mov     rax, [rdi+730h]
0x18001f287  mov     edx, r12d
0x18001f28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f28f  mov     ebx, eax
0x18001f291  test    eax, eax
0x18001f293  js      short loc_18001F2F2
0x18001f295  mov     rcx, [rbp+3Fh+var_60]
0x18001f299  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f29d  inc     rax
0x18001f2a0  cmp     [rcx+rax*2], r13w
0x18001f2a5  jnz     short loc_18001F29D
0x18001f2a7  inc     eax
0x18001f2a9  mov     esi, eax
0x18001f2ab  lea     rbx, [rax+rax]
0x18001f2af  call    cs:__imp_GetProcessHeap
0x18001f2b5  mov     r8, rbx; dwBytes
0x18001f2b8  mov     edx, 8; dwFlags
0x18001f2bd  mov     rcx, rax; hHeap
0x18001f2c0  call    cs:__imp_HeapAlloc
0x18001f2c6  mov     [r15], rax
0x18001f2c9  test    rax, rax
0x18001f2cc  jz      loc_18001F1AC
0x18001f2d2  mov     r8, [rbp+3Fh+var_60]; unsigned __int16 *
0x18001f2d6  mov     edx, esi; unsigned __int64
0x18001f2d8  mov     rcx, rax; unsigned __int16 *
0x18001f2db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f2e0  mov     ebx, eax
0x18001f2e2  test    eax, eax
0x18001f2e4  js      short loc_18001F2F2
0x18001f2e6  mov     ebx, 80070005h
0x18001f2eb  jmp     short loc_18001F2F2
0x18001f2ed  mov     ebx, 80004005h
0x18001f2f2  mov     rcx, [rbp+3Fh+var_70]
0x18001f2f6  test    rcx, rcx
0x18001f2f9  jz      short loc_18001F307
0x18001f2fb  mov     rax, [rdi+718h]
0x18001f302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f307  mov     rcx, [rbp+3Fh+var_78]
0x18001f30b  test    rcx, rcx
0x18001f30e  jz      short loc_18001F31C
0x18001f310  mov     rax, [rdi+6F0h]
0x18001f317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f31c  mov     rcx, [rbp+3Fh+var_58]
0x18001f320  test    rcx, rcx
0x18001f323  jz      short loc_18001F331
0x18001f325  mov     rax, [rdi+740h]
0x18001f32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f331  mov     eax, ebx
0x18001f333  add     rsp, 88h
0x18001f33a  pop     r15
0x18001f33c  pop     r14
0x18001f33e  pop     r13
0x18001f340  pop     r12
0x18001f342  pop     rdi
0x18001f343  pop     rsi
0x18001f344  pop     rbx
0x18001f345  pop     rbp
0x18001f346  retn
```
