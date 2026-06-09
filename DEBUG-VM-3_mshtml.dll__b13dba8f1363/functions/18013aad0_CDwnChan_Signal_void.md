# CDwnChan::Signal(void)

- ea: `0x18013aad0`
- end: `0x18013ac34`
- name: `?Signal@CDwnChan@@IEAAXXZ`
- size: `356`
- prototype: `void __fastcall(CDwnChan *__hidden this)`
- caller_count: `18`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180137dc8`
- `0x18013878c`
- `0x18013aaa4`
- `0x1803022f4`
- `0x180496450`
- `0x1804e192c`
- `0x1804e2430`
- `0x18051f410`
- `0x1805fbe84`
- `0x18062bb30`
- `0x18064bb20`
- `0x18065bf68`
- `0x180664880`
- `0x18066bbd4`
- `0x1806ae96c`
- `0x1806b3a64`
- `0x180a23190`
- `0x180a2b840`

## callees

- `0x18013aad0`
- `0x1801a194c`
- `0x1807c4fcc`
- `0x1807ce540`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18013abc6`
- `KERNEL32!GetCurrentThreadId` at `0x18013abc6`
- `KERNEL32!LeaveCriticalSection` at `0x18013aba4`
- `KERNEL32!LeaveCriticalSection` at `0x18013aba4`
- `KERNEL32!EnterCriticalSection` at `0x18013ab53`
- `KERNEL32!EnterCriticalSection` at `0x18013ab53`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013ab25`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013ab2e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013ab38`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013ab42`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013abaa`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013abb4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013ab25`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013ab2e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013ab38`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013ab42`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013abaa`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18013abb4`

## pseudocode

```c
void __fastcall CDwnChan::Signal(CDwnChan *this)
{
  __int128 v2; // xmm6
  __int128 v3; // xmm7
  char v4; // bp
  bool v5; // zf
  int v6; // esi
  int v7; // ebx
  __int64 v8; // rcx
  _BYTE v9[8]; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int64 v10; // [rsp+40h] [rbp-68h]
  _BYTE v11[8]; // [rsp+48h] [rbp-60h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp-58h]

  if ( !*((_DWORD *)this + 6) )
  {
    v2 = *(_OWORD *)((char *)this + 60);
    v3 = *(_OWORD *)GlobalThreadState();
    v4 = *((_BYTE *)GlobalThreadState() + 16);
    *(_OWORD *)GlobalThreadState() = v2;
    *((_BYTE *)GlobalThreadState() + 16) = 1;
    EnterCriticalSection(&g_csDwnChanSig);
    if ( !*((_DWORD *)this + 6) )
    {
      v5 = *((_BYTE *)this + 28) == 0;
      v6 = 1;
      *((_DWORD *)this + 6) = 1;
      if ( !v5 )
      {
        v7 = *((_DWORD *)this + 14);
        if ( v7 == GetCurrentThreadId() )
          v6 = 3;
      }
      if ( (Microsoft_IEEnableBits & 0x100000000LL) != 0 )
      {
        DDT_ATOM(v9, "!Request");
        v10 = 0xC003030000000000uLL;
        DDT_ATOM(v11, "Document");
        v12 = 0xC004090300000000uLL;
        McTemplateU0hbr0_EventWriteTransfer(v8, MSHTML_DDTRACKER_INFO, 32, v9);
      }
      _GWPostMethodCallEx(
        *((struct GWND **)this + 6),
        (unsigned __int64)this,
        (__int64)CDwnChan::OnMethodCall,
        0,
        v6,
        0);
    }
    LeaveCriticalSection(&g_csDwnChanSig);
    *(_OWORD *)GlobalThreadState() = v3;
    *((_BYTE *)GlobalThreadState() + 16) = v4;
  }
}

```

## disassembly

```asm
0x18013aad0  push    rbx
0x18013aad2  push    rbp
0x18013aad3  push    rsi
0x18013aad4  push    rdi
0x18013aad5  sub     rsp, 88h
0x18013aadc  movaps  [rsp+0A8h+var_38], xmm6
0x18013aae1  movaps  [rsp+0A8h+var_48], xmm7
0x18013aae6  mov     rax, cs:__security_cookie
0x18013aaed  xor     rax, rsp
0x18013aaf0  mov     [rsp+0A8h+var_50], rax
0x18013aaf5  cmp     dword ptr [rcx+18h], 0
0x18013aaf9  mov     rdi, rcx
0x18013aafc  jz      short loc_18013AB21
0x18013aafe  mov     rcx, [rsp+0A8h+var_50]
0x18013ab03  xor     rcx, rsp; StackCookie
0x18013ab06  call    __security_check_cookie
0x18013ab0b  movaps  xmm6, [rsp+0A8h+var_38]
0x18013ab10  movaps  xmm7, [rsp+0A8h+var_48]
0x18013ab15  add     rsp, 88h
0x18013ab1c  pop     rdi
0x18013ab1d  pop     rsi
0x18013ab1e  pop     rbp
0x18013ab1f  pop     rbx
0x18013ab20  retn
0x18013ab21  movups  xmm6, xmmword ptr [rcx+3Ch]
0x18013ab25  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18013ab2b  movups  xmm7, xmmword ptr [rax]
0x18013ab2e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18013ab34  mov     bpl, [rax+10h]
0x18013ab38  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18013ab3e  movdqu  xmmword ptr [rax], xmm6
0x18013ab42  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18013ab48  lea     rcx, ?g_csDwnChanSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18013ab4f  mov     byte ptr [rax+10h], 1
0x18013ab53  call    cs:__imp_EnterCriticalSection
0x18013ab59  cmp     dword ptr [rdi+18h], 0
0x18013ab5d  jnz     short loc_18013AB9D
0x18013ab5f  cmp     byte ptr [rdi+1Ch], 0
0x18013ab63  mov     esi, 1
0x18013ab68  mov     dword ptr [rdi+18h], 1
0x18013ab6f  jnz     short loc_18013ABC3
0x18013ab71  test    byte ptr cs:Microsoft_IEEnableBits+4, 1
0x18013ab78  jnz     short loc_18013ABD8
0x18013ab7a  mov     rcx, [rdi+30h]; struct GWND *
0x18013ab7e  lea     r8, ?OnMethodCall@CDwnChan@@IEAAX_K@Z; CDwnChan::OnMethodCall(unsigned __int64)
0x18013ab85  mov     [rsp+0A8h+var_80], 0; __int64
0x18013ab8e  xor     r9d, r9d
0x18013ab91  mov     rdx, rdi
0x18013ab94  mov     [rsp+0A8h+var_88], esi; int
0x18013ab98  call    ?_GWPostMethodCallEx@@YAJPEAVGWND@@PEAXP8CVoid@@EAAX_K@Z2KP6AX2@Z@Z; _GWPostMethodCallEx(GWND *,void *,void (CVoid::*)(unsigned __int64),unsigned __int64,ulong,void (*)(unsigned __int64))
0x18013ab9d  lea     rcx, ?g_csDwnChanSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18013aba4  call    cs:__imp_LeaveCriticalSection
0x18013abaa  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18013abb0  movdqu  xmmword ptr [rax], xmm7
0x18013abb4  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18013abba  mov     [rax+10h], bpl
0x18013abbe  jmp     loc_18013AAFE
0x18013abc3  mov     ebx, [rdi+38h]
0x18013abc6  call    cs:__imp_GetCurrentThreadId
0x18013abcc  cmp     ebx, eax
0x18013abce  mov     ecx, 3
0x18013abd3  cmovz   esi, ecx
0x18013abd6  jmp     short loc_18013AB71
0x18013abd8  lea     rdx, aRequest; "!Request"
0x18013abdf  lea     rcx, [rsp+0A8h+var_70]
0x18013abe4  call    ?DDT_ATOM@@YA?AUDdtAtom@@PEBD@Z; DDT_ATOM(char const *)
0x18013abe9  mov     rax, 0C003030000000000h
0x18013abf3  lea     rdx, aDocument; "Document"
0x18013abfa  lea     rcx, [rsp+0A8h+var_60]
0x18013abff  mov     [rsp+0A8h+var_68], rax
0x18013ac04  call    ?DDT_ATOM@@YA?AUDdtAtom@@PEBD@Z; DDT_ATOM(char const *)
0x18013ac09  mov     rax, 0C004090300000000h
0x18013ac13  lea     r9, [rsp+0A8h+var_70]
0x18013ac18  mov     r8d, 20h ; ' '
0x18013ac1e  mov     [rsp+0A8h+var_58], rax
0x18013ac23  lea     rdx, MSHTML_DDTRACKER_INFO
0x18013ac2a  call    McTemplateU0hbr0_EventWriteTransfer
0x18013ac2f  jmp     loc_18013AB7A
```
