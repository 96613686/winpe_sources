# DsPrivLogCamera_GetHookAPIs

- ea: `0x180033310`
- end: `0x1800333e9`
- name: `DsPrivLogCamera_GetHookAPIs`
- size: `217`
- prototype: `struct tagHOOKAPI *__fastcall(__int64, wchar_t *, _DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001bfe8`
- `0x18002606c`
- `0x180033310`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180033383`
- `ntdll!RtlAllocateHeap` at `0x180033383`

## string_xrefs

- `0x1800333a0`: `AVICAP32.DLL`
- `0x1800333b5`: `capCreateCaptureWindowW`
- `0x180033395`: `capCreateCaptureWindowA`

## pseudocode

```c
struct tagHOOKAPI *__fastcall DsPrivLogCamera_GetHookAPIs(__int64 a1, wchar_t *a2, _DWORD *a3)
{
  struct tagHOOKAPI *result; // rax
  bool v5; // zf

  result = 0;
  v5 = dword_180081068 == 0;
  NS_PrivLogCamera::g_pAPIHooks = 0;
  *a3 = 0;
  if ( v5 )
  {
    if ( (unsigned int)DsInitialize() )
    {
      return NS_PrivLogCamera::g_pAPIHooks;
    }
    else
    {
      dword_180081068 = 1;
      if ( !qword_180081050 && a2 )
        qword_180081050 = DsUtilityDuplicateStringW(a2);
      result = (struct tagHOOKAPI *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x60u);
      NS_PrivLogCamera::g_pAPIHooks = result;
      if ( result )
      {
        *((_QWORD *)result + 1) = "capCreateCaptureWindowA";
        *(_QWORD *)result = "AVICAP32.DLL";
        *((_QWORD *)result + 2) = NS_PrivLogCamera::APIHook_capCreateCaptureWindowA;
        *((_QWORD *)result + 7) = "capCreateCaptureWindowW";
        *((_QWORD *)result + 8) = NS_PrivLogCamera::APIHook_capCreateCaptureWindowW;
        *((_QWORD *)result + 6) = "AVICAP32.DLL";
        *a3 = 2;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180033310  mov     [rsp+arg_0], rbx
0x180033315  push    rdi
0x180033316  sub     rsp, 20h
0x18003331a  xor     eax, eax
0x18003331c  mov     rdi, r8
0x18003331f  cmp     cs:dword_180081068, eax
0x180033325  mov     rbx, rdx
0x180033328  mov     cs:?g_pAPIHooks@NS_PrivLogCamera@@3PEAUtagHOOKAPI@@EA, rax; tagHOOKAPI * NS_PrivLogCamera::g_pAPIHooks
0x18003332f  mov     [r8], eax
0x180033332  jnz     loc_1800333DE
0x180033338  call    DsInitialize
0x18003333d  test    eax, eax
0x18003333f  jnz     loc_1800333D7
0x180033345  cmp     cs:qword_180081050, 0
0x18003334d  mov     cs:dword_180081068, 1
0x180033357  jnz     short loc_18003336D
0x180033359  test    rbx, rbx
0x18003335c  jz      short loc_18003336D
0x18003335e  mov     rcx, rbx; Source
0x180033361  call    DsUtilityDuplicateStringW
0x180033366  mov     cs:qword_180081050, rax
0x18003336d  mov     rcx, gs:60h
0x180033376  mov     edx, 8; Flags
0x18003337b  mov     rcx, [rcx+30h]; HeapHandle
0x18003337f  lea     r8d, [rdx+58h]; Size
0x180033383  call    cs:__imp_RtlAllocateHeap
0x180033389  mov     cs:?g_pAPIHooks@NS_PrivLogCamera@@3PEAUtagHOOKAPI@@EA, rax; tagHOOKAPI * NS_PrivLogCamera::g_pAPIHooks
0x180033390  test    rax, rax
0x180033393  jz      short loc_1800333DE
0x180033395  lea     rcx, aCapcreatecaptu_0; "capCreateCaptureWindowA"
0x18003339c  mov     [rax+8], rcx
0x1800333a0  lea     rdx, aAvicap32Dll; "AVICAP32.DLL"
0x1800333a7  lea     rcx, ?APIHook_capCreateCaptureWindowA@NS_PrivLogCamera@@YAJPEBDKHHHHPEAUHWND__@@H@Z; NS_PrivLogCamera::APIHook_capCreateCaptureWindowA(char const *,ulong,int,int,int,int,HWND__ *,int)
0x1800333ae  mov     [rax], rdx
0x1800333b1  mov     [rax+10h], rcx
0x1800333b5  lea     rcx, aCapcreatecaptu; "capCreateCaptureWindowW"
0x1800333bc  mov     [rax+38h], rcx
0x1800333c0  lea     rcx, ?APIHook_capCreateCaptureWindowW@NS_PrivLogCamera@@YAJPEBGKHHHHPEAUHWND__@@H@Z; NS_PrivLogCamera::APIHook_capCreateCaptureWindowW(ushort const *,ulong,int,int,int,int,HWND__ *,int)
0x1800333c7  mov     [rax+40h], rcx
0x1800333cb  mov     [rax+30h], rdx
0x1800333cf  mov     dword ptr [rdi], 2
0x1800333d5  jmp     short loc_1800333DE
0x1800333d7  mov     rax, cs:?g_pAPIHooks@NS_PrivLogCamera@@3PEAUtagHOOKAPI@@EA; tagHOOKAPI * NS_PrivLogCamera::g_pAPIHooks
0x1800333de  mov     rbx, [rsp+28h+arg_0]
0x1800333e3  add     rsp, 20h
0x1800333e7  pop     rdi
0x1800333e8  retn
```
