# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::DeferredWorkEventCallback(_ACTIVITY_COORDINATOR_NOTIFICATION,void *)

- ea: `0x1800053f0`
- end: `0x180005490`
- name: `?DeferredWorkEventCallback@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@SAXW4_ACTIVITY_COORDINATOR_NOTIFICATION@@PEAX@Z`
- size: `160`
- prototype: `int __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800053f0`
- `0x180012a40`
- `0x180017308`
- `0x1800181fc`
- `0x18001cca0`

## string_xrefs

- `0x180005479`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.Private.CacheManagement\ModelCacheManager.cpp`

## pseudocode

```c
int __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::DeferredWorkEventCallback(
        int a1,
        __int64 a2)
{
  int result; // eax
  const char *v4; // [rsp+28h] [rbp-30h]
  _QWORD *v5; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    return wil::details::in1diag3::Log_HrMsg(
             retaddr,
             (void *)0x6D,
             (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
             (const char *)0x8000FFFFLL,
             (int)"DeferredWorkEventCallback context is null.",
             v4);
  if ( a1 )
  {
    result = *(unsigned __int8 *)(a2 + 232);
    if ( !(_BYTE)result )
    {
      *(_BYTE *)(a2 + 232) = 1;
      return Cnd_broadcast((_Cnd_t)(a2 + 160));
    }
  }
  else
  {
    v5 = operator new(0x30u);
    v5[5] = a2;
    *v5 = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWorkAsync__ResumeCoro_1;
    *((_DWORD *)v5 + 2) = 65538;
    *((_BYTE *)v5 + 32) = 0;
    return winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::RunCacheWorkAsync__ResumeCoro_1(v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800053f0  push    rbx
0x1800053f2  sub     rsp, 50h
0x1800053f6  mov     rbx, rdx
0x1800053f9  test    rdx, rdx
0x1800053fc  jz      short loc_180005462
0x1800053fe  test    ecx, ecx
0x180005400  jnz     short loc_18000543A
0x180005402  mov     ecx, 30h ; '0'; Size
0x180005407  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000540c  mov     [rsp+58h+var_28], rax
0x180005411  mov     [rax+28h], rbx
0x180005415  lea     rcx, winrt__Microsoft__Windows__Private__CacheManagement__implementation__ModelCacheManager__RunCacheWorkAsync$_ResumeCoro$1
0x18000541c  mov     [rax], rcx
0x18000541f  mov     dword ptr [rax+8], 10002h
0x180005426  xor     ecx, ecx
0x180005428  mov     [rax+20h], cl
0x18000542b  mov     rcx, rax
0x18000542e  call    winrt__Microsoft__Windows__Private__CacheManagement__implementation__ModelCacheManager__RunCacheWorkAsync$_ResumeCoro$1
0x180005433  nop
0x180005434  add     rsp, 50h
0x180005438  pop     rbx
0x180005439  retn
0x18000543a  movzx   eax, byte ptr [rdx+0E8h]
0x180005441  test    al, al
0x180005443  jnz     short loc_18000548A
0x180005445  mov     eax, 1
0x18000544a  xchg    al, [rdx+0E8h]
0x180005450  lea     rcx, [rdx+0A0h]; _Cnd_t
0x180005457  call    _Cnd_broadcast
0x18000545c  add     rsp, 50h
0x180005460  pop     rbx
0x180005461  retn
0x180005462  mov     rcx, [rsp+58h]; this
0x180005467  lea     rax, aDeferredworkev; "DeferredWorkEventCallback context is nu"...
0x18000546e  mov     qword ptr [rsp+58h+var_38], rax; int
0x180005473  mov     r9d, 8000FFFFh; char *
0x180005479  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180005480  mov     edx, 6Dh ; 'm'; void *
0x180005485  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000548a  add     rsp, 50h
0x18000548e  pop     rbx
0x18000548f  retn
```
