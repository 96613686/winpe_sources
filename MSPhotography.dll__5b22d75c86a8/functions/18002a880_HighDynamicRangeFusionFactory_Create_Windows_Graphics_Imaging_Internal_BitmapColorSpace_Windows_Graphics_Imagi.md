# HighDynamicRangeFusionFactory::Create(Windows::Graphics::Imaging::Internal::BitmapColorSpace,Windows::Graphics::Imaging::Internal::IHighDynamicRangeFusion * *)

- ea: `0x18002a880`
- end: `0x18002a9b3`
- name: `?Create@HighDynamicRangeFusionFactory@@UEAAJW4BitmapColorSpace@Internal@Imaging@Graphics@Windows@@PEAPEAUIHighDynamicRangeFusion@3456@@Z`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18002a69c`
- `0x18002a880`
- `0x18002a9bc`
- `0x18002aa84`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a8aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a93f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a8aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a93f`

## string_xrefs

- `0x18002a99c`: `HighDynamicRangeFusionFactory::Create`

## pseudocode

```c
__int64 __fastcall HighDynamicRangeFusionFactory::Create(__int64 a1, int a2, _QWORD *a3)
{
  int v3; // eax
  __int64 *v4; // rcx
  int v5; // ebx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v8; // r8d
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  int v12; // [rsp+38h] [rbp+10h] BYREF

  v12 = a2;
  if ( a3 )
  {
    *a3 = 0;
    v5 = Microsoft::WRL::Details::MakeAndInitialize<HighDynamicRangeFusionImpl,Windows::Graphics::Imaging::Internal::IHighDynamicRangeFusion,enum Windows::Graphics::Imaging::Internal::BitmapColorSpace &>(
           a3,
           &v12);
    if ( v5 < 0 )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        {
          v8 = 39;
          goto LABEL_20;
        }
      }
    }
  }
  else
  {
    v3 = MF::OriginateError((MF *)0x80004003LL, a2);
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = v3;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( v5 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v5 )
      {
        v8 = 36;
LABEL_20:
        CallStackContext::TraceFailure(ThreadRelativeContext, "HighDynamicRangeFusionFactory::Create", v8, v5);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a880  mov     [rsp+arg_8], edx
0x18002a884  push    rbx
0x18002a885  sub     rsp, 20h
0x18002a889  test    r8, r8
0x18002a88c  jnz     loc_18002A919
0x18002a892  mov     ecx, 80004003h; this
0x18002a897  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18002a89c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8a3  mov     ebx, eax
0x18002a8a5  test    rcx, rcx
0x18002a8a8  jnz     short loc_18002A8EB
0x18002a8aa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a8b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8b7  mov     rcx, rax
0x18002a8ba  test    rax, rax
0x18002a8bd  jz      short loc_18002A8DD
0x18002a8bf  mov     rdx, [rax]
0x18002a8c2  mov     rax, [rdx+8]
0x18002a8c6  mov     edx, 7F0h
0x18002a8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8d0  test    eax, eax
0x18002a8d2  jz      short loc_18002A8DD
0x18002a8d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8db  jmp     short loc_18002A8EB
0x18002a8dd  lea     rcx, qword_18015FF10; this
0x18002a8e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8eb  cmp     byte ptr [rcx+8], 0
0x18002a8ef  jz      loc_18002A9AB
0x18002a8f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a8fa  test    ebx, ebx
0x18002a8fc  jns     loc_18002A9AB
0x18002a902  cmp     [rax+7CCh], ebx
0x18002a908  jz      loc_18002A9AB
0x18002a90e  mov     r8d, 24h ; '$'
0x18002a914  jmp     loc_18002A999
0x18002a919  lea     rdx, [rsp+28h+arg_8]
0x18002a91e  mov     qword ptr [r8], 0
0x18002a925  mov     rcx, r8
0x18002a928  call    ??$MakeAndInitialize@VHighDynamicRangeFusionImpl@@UIHighDynamicRangeFusion@Internal@Imaging@Graphics@Windows@@AEAW4BitmapColorSpace@3456@@Details@WRL@Microsoft@@YAJPEAPEAUIHighDynamicRangeFusion@Internal@Imaging@Graphics@Windows@@AEAW4BitmapColorSpace@4567@@Z; Microsoft::WRL::Details::MakeAndInitialize<HighDynamicRangeFusionImpl,Windows::Graphics::Imaging::Internal::IHighDynamicRangeFusion,Windows::Graphics::Imaging::Internal::BitmapColorSpace &>(Windows::Graphics::Imaging::Internal::IHighDynamicRangeFusion * *,Windows::Graphics::Imaging::Internal::BitmapColorSpace &)
0x18002a92d  mov     ebx, eax
0x18002a92f  test    eax, eax
0x18002a931  jns     short loc_18002A9AB
0x18002a933  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a93a  test    rcx, rcx
0x18002a93d  jnz     short loc_18002A980
0x18002a93f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a945  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a94c  mov     rcx, rax
0x18002a94f  test    rax, rax
0x18002a952  jz      short loc_18002A972
0x18002a954  mov     rax, [rax]
0x18002a957  mov     edx, 7F0h
0x18002a95c  mov     rax, [rax+8]
0x18002a960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a965  test    eax, eax
0x18002a967  jz      short loc_18002A972
0x18002a969  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a970  jmp     short loc_18002A980
0x18002a972  lea     rcx, qword_18015FF10; this
0x18002a979  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a980  cmp     byte ptr [rcx+8], 0
0x18002a984  jz      short loc_18002A9AB
0x18002a986  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a98b  cmp     [rax+7CCh], ebx
0x18002a991  jz      short loc_18002A9AB
0x18002a993  mov     r8d, 27h ; '''; int
0x18002a999  mov     r9d, ebx; int
0x18002a99c  lea     rdx, aHighdynamicran_2; "HighDynamicRangeFusionFactory::Create"
0x18002a9a3  mov     rcx, rax; this
0x18002a9a6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a9ab  mov     eax, ebx
0x18002a9ad  add     rsp, 20h
0x18002a9b1  pop     rbx
0x18002a9b2  retn
```
