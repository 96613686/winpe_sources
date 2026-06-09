# Windows::UI::Composition::CompositionObject::RuntimeClassInitialize(Windows::UI::Composition::Compositor *)

- ea: `0x180014e80`
- end: `0x18001500b`
- name: `?RuntimeClassInitialize@CompositionObject@Composition@UI@Windows@@QEAAJPEAVCompositor@234@@Z`
- size: `395`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CompositionObject *__hidden this, struct Windows::UI::Composition::Compositor *)`
- caller_count: `48`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f960`
- `0x1800178e4`
- `0x18002a008`
- `0x18002bc18`
- `0x1800338a8`
- `0x18003b770`
- `0x180045864`
- `0x18004a9f0`
- `0x18004f614`
- `0x18004f9bc`
- `0x180051de8`
- `0x1800536d8`
- `0x180053d98`
- `0x18005e744`
- `0x18005e8b4`
- `0x18005ee64`
- `0x1800737d0`
- `0x180078580`
- `0x180096940`
- `0x180096b00`
- `0x180096d38`
- `0x180099980`
- `0x180099c80`
- `0x180099f14`
- `0x18009f4fc`
- `0x18009ff50`
- `0x1800a1480`
- `0x1800a2af0`
- `0x1800b6340`
- `0x1800b9f7c`
- `0x1800c8de0`
- `0x1800d4ad0`
- `0x1800d9934`
- `0x1800dfe6c`
- `0x1800ea41c`
- `0x1800ead98`
- `0x180118804`
- `0x18011ec34`
- `0x18011ffac`
- `0x18012e93c`
- `0x18012f6fc`
- `0x1801317d8`
- `0x180133288`
- `0x1801335cc`
- `0x180142d50`
- `0x1801514d4`
- `0x18015b1d0`
- `0x180172cb8`

## callees

- `0x180012da0`
- `0x18001358c`
- `0x180014e80`
- `0x180036f90`
- `0x18003ced8`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014ec2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014ec2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180014f08`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180014f08`

## string_xrefs

- `0x180014efa`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180014fba`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionObject::RuntimeClassInitialize(
        Windows::UI::Composition::CompositionObject *this,
        struct Windows::UI::Composition::Compositor *a2)
{
  int v4; // edi
  Microsoft::WRL2::ContextSession *v5; // rcx
  struct Windows::UI::Composition::Compositor **v6; // r8
  char v7; // cl
  int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // edi
  char v11; // al
  bool v12; // zf
  int v13; // eax
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *((_QWORD *)this + 3) = a2;
  if ( a2 != this )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)a2 + 4) == 1 )
      (*(void (__fastcall **)(struct Windows::UI::Composition::Compositor *))(*(_QWORD *)a2 + 80LL))(a2);
    v4 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 56LL) + 40LL);
    if ( v4 == GetCurrentThreadId() )
    {
      v5 = 0;
    }
    else
    {
      Microsoft::WRL2::ContextSession::BeginApiEntry(*((Microsoft::WRL2::ContextSession **)a2 + 3));
      v5 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)a2 + 3);
      if ( (*((_BYTE *)a2 + 48) & 2) == 0 )
      {
        Microsoft::WRL2::ContextSession::EndApiEntry(v5);
        RoOriginateErrorW(
          2147483667LL,
          0,
          L"The given object has already been closed / disposed and may no longer be used.");
        goto LABEL_12;
      }
    }
    v6 = (struct Windows::UI::Composition::Compositor **)*((_QWORD *)a2 + 5);
    if ( *v6 != (struct Windows::UI::Composition::Compositor *)((char *)a2 + 32) )
      __fastfail(3u);
    *((_QWORD *)this + 4) = (char *)a2 + 32;
    *((_QWORD *)this + 5) = v6;
    *v6 = (Windows::UI::Composition::CompositionObject *)((char *)this + 32);
    *((_QWORD *)a2 + 5) = (char *)this + 32;
    if ( v5 )
      Microsoft::WRL2::ContextSession::EndApiEntry(v5);
  }
LABEL_12:
  v7 = *((_BYTE *)this + 49);
  *((_BYTE *)this + 48) = 31;
  *((_BYTE *)this + 49) ^= (*((_BYTE *)a2 + 49) ^ v7) & 1;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, Windows::UI::Composition::CompositionObject *, char *))(**(_QWORD **)(*((_QWORD *)a2 + 51) + 32LL) + 24LL))(
         *(_QWORD *)(*((_QWORD *)a2 + 51) + 32LL),
         *(unsigned int *)(*((_QWORD *)a2 + 51) + 64LL),
         this,
         (char *)this + 136);
  v10 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
      (const char *)(unsigned int)v8,
      v15);
    return v10;
  }
  else
  {
    v11 = *((_BYTE *)a2 + 436);
    if ( (v11 & 1) == 0 )
    {
      v12 = *((_DWORD *)a2 + 108) == 0;
      *((_BYTE *)a2 + 436) = v11 | 1;
      if ( v12 )
      {
        LOBYTE(v9) = 1;
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a2 + 52) + 48LL))(*((_QWORD *)a2 + 52), v9);
        if ( v13 < 0 )
          Microsoft::WRL2::FailFast::ForHR(v13, retaddr);
      }
    }
    *((_DWORD *)this + 35) |= 1u;
    return 0;
  }
}

```

## disassembly

```asm
0x180014e80  mov     [rsp+arg_0], rbx
0x180014e85  mov     [rsp+arg_8], rsi
0x180014e8a  push    rdi
0x180014e8b  sub     rsp, 30h
0x180014e8f  mov     [rcx+18h], rdx
0x180014e93  mov     rbx, rdx
0x180014e96  mov     rsi, rcx
0x180014e99  cmp     rdx, rcx
0x180014e9c  jz      loc_180014F2C
0x180014ea2  mov     eax, 1
0x180014ea7  lock xadd [rdx+10h], eax
0x180014eac  inc     eax
0x180014eae  cmp     eax, 1
0x180014eb1  jz      loc_180014FE0
0x180014eb7  mov     rax, [rbx+18h]
0x180014ebb  mov     rcx, [rax+38h]
0x180014ebf  mov     edi, [rcx+28h]
0x180014ec2  call    cs:__imp_GetCurrentThreadId
0x180014ec8  cmp     edi, eax
0x180014eca  jnz     short loc_180014EE2
0x180014ecc  xor     ecx, ecx; this
0x180014ece  mov     r8, [rbx+28h]
0x180014ed2  lea     rdx, [rbx+20h]
0x180014ed6  cmp     [r8], rdx
0x180014ed9  jz      short loc_180014F10
0x180014edb  mov     ecx, 3
0x180014ee0  int     29h; Win8: RtlFailFast(ecx)
0x180014ee2  mov     rcx, [rbx+18h]; this
0x180014ee6  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180014eeb  test    byte ptr [rbx+30h], 2
0x180014eef  mov     rcx, [rbx+18h]; this
0x180014ef3  jnz     short loc_180014ECE
0x180014ef5  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180014efa  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180014f01  xor     edx, edx
0x180014f03  mov     ecx, 80000013h
0x180014f08  call    cs:__imp_RoOriginateErrorW
0x180014f0e  jmp     short loc_180014F2C
0x180014f10  mov     [rsi+20h], rdx
0x180014f14  lea     rax, [rsi+20h]
0x180014f18  mov     [rax+8], r8
0x180014f1c  mov     [r8], rax
0x180014f1f  mov     [rdx+8], rax
0x180014f23  test    rcx, rcx
0x180014f26  jnz     loc_180014FF4
0x180014f2c  movzx   ecx, byte ptr [rsi+31h]
0x180014f30  lea     r9, [rsi+88h]
0x180014f37  mov     byte ptr [rsi+30h], 1Fh
0x180014f3b  mov     r8, rsi
0x180014f3e  xor     cl, [rbx+31h]
0x180014f41  and     cl, 1
0x180014f44  xor     [rsi+31h], cl
0x180014f47  mov     rdx, [rbx+198h]
0x180014f4e  mov     rcx, [rdx+20h]
0x180014f52  mov     edx, [rdx+40h]
0x180014f55  mov     rax, [rcx]
0x180014f58  mov     rax, [rax+18h]
0x180014f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f61  mov     edi, eax
0x180014f63  test    eax, eax
0x180014f65  js      short loc_180014FB5
0x180014f67  movzx   eax, byte ptr [rbx+1B4h]
0x180014f6e  test    al, 1
0x180014f70  jnz     short loc_180014F9C
0x180014f72  or      al, 1
0x180014f74  cmp     dword ptr [rbx+1B0h], 0
0x180014f7b  mov     [rbx+1B4h], al
0x180014f81  jnz     short loc_180014F9C
0x180014f83  mov     rcx, [rbx+1A0h]
0x180014f8a  mov     dl, 1
0x180014f8c  mov     rax, [rcx]
0x180014f8f  mov     rax, [rax+30h]
0x180014f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f98  test    eax, eax
0x180014f9a  js      short loc_180014FFE
0x180014f9c  or      dword ptr [rsi+8Ch], 1
0x180014fa3  xor     eax, eax
0x180014fa5  mov     rbx, [rsp+38h+arg_0]
0x180014faa  mov     rsi, [rsp+38h+arg_8]
0x180014faf  add     rsp, 30h
0x180014fb3  pop     rdi
0x180014fb4  retn
0x180014fb5  mov     rcx, [rsp+38h]; this
0x180014fba  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180014fc1  mov     r9d, edi; char *
0x180014fc4  mov     edx, 55h ; 'U'; void *
0x180014fc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014fce  mov     rbx, [rsp+38h+arg_0]
0x180014fd3  mov     eax, edi
0x180014fd5  mov     rsi, [rsp+38h+arg_8]
0x180014fda  add     rsp, 30h
0x180014fde  pop     rdi
0x180014fdf  retn
0x180014fe0  mov     rax, [rdx]
0x180014fe3  mov     rcx, rbx
0x180014fe6  mov     rax, [rax+50h]
0x180014fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fef  jmp     loc_180014EB7
0x180014ff4  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180014ff9  jmp     loc_180014F2C
0x180014ffe  mov     rdx, [rsp+38h]; void *
0x180015003  mov     ecx, eax; int
0x180015005  call    ?ForHR@FailFast@WRL2@Microsoft@@SAXJPEBX@Z; Microsoft::WRL2::FailFast::ForHR(long,void const *)
```
