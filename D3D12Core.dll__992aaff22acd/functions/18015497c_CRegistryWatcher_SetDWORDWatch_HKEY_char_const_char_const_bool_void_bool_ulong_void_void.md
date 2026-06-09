# CRegistryWatcher::SetDWORDWatch(HKEY__ *,char const *,char const *,bool,void (*)(bool,ulong,void *),void *)

- ea: `0x18015497c`
- end: `0x180154a3f`
- name: `?SetDWORDWatch@CRegistryWatcher@@QEAAJPEAUHKEY__@@PEBD1_NP6AX2KPEAX@Z3@Z`
- size: `195`
- prototype: `__int64 __usercall@<rax>(CRegistryWatcher *__hidden this@<rcx>, HKEY@<rdx>, const char *@<r8>, const char *@<r9>, bool, void (*)(bool, unsigned int, void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800602dc`

## callees

- `0x18002b050`
- `0x180074ef4`
- `0x18015497c`
- `0x180154a74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801549c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801549c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1801549e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1801549e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801549b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801549b0`

## pseudocode

```c
__int64 __fastcall CRegistryWatcher::SetDWORDWatch(
        CRegistryWatcher *this,
        HKEY a2,
        const char *a3,
        const char *a4,
        bool a5,
        void (*a6)(bool, unsigned int, void *),
        void *a7)
{
  unsigned int v7; // ebx
  HANDLE EventA; // rax
  PTP_WAIT ThreadpoolWait; // rax

  v7 = 0;
  if ( !*((_QWORD *)this + 4)
    && !RegOpenKeyExA(HKEY_LOCAL_MACHINE, a3, 0, 0x111u, (PHKEY)this + 3)
    && (EventA = CreateEventA(0, 1, 0, 0), (*((_QWORD *)this + 4) = EventA) != 0)
    && (ThreadpoolWait = CreateThreadpoolWait(WaitCallback, this, 0), (*(_QWORD *)this = ThreadpoolWait) != 0) )
  {
    *((_QWORD *)this + 1) = RegistryDeveloperModeChangedCallback;
    *((_QWORD *)this + 2) = a7;
    StringCchCopyA((char *)this + 40, 0x104u, "AllowDevelopmentWithoutDevLicense");
    WaitWorker(this, *(struct _TP_WAIT **)this);
  }
  else
  {
    v7 = -2147467259;
    CRegistryWatcher::Cleanup(this);
  }
  return v7;
}

```

## disassembly

```asm
0x18015497c  mov     [rsp+arg_0], rbx
0x180154981  push    rdi
0x180154982  sub     rsp, 30h
0x180154986  xor     ebx, ebx
0x180154988  mov     r10, r8
0x18015498b  mov     rdi, rcx
0x18015498e  cmp     [rcx+20h], rbx
0x180154992  jnz     short loc_1801549EF
0x180154994  lea     rax, [rcx+18h]
0x180154998  mov     r9d, 111h; samDesired
0x18015499e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801549a5  mov     [rsp+38h+phkResult], rax; phkResult
0x1801549aa  xor     r8d, r8d; ulOptions
0x1801549ad  mov     rdx, r10; lpSubKey
0x1801549b0  call    cs:__imp_RegOpenKeyExA
0x1801549b6  test    eax, eax
0x1801549b8  jnz     short loc_1801549EF
0x1801549ba  xor     r9d, r9d; lpName
0x1801549bd  lea     edx, [rbx+1]; bManualReset
0x1801549c0  xor     r8d, r8d; bInitialState
0x1801549c3  xor     ecx, ecx; lpEventAttributes
0x1801549c5  call    cs:__imp_CreateEventA
0x1801549cb  mov     [rdi+20h], rax
0x1801549cf  test    rax, rax
0x1801549d2  jz      short loc_1801549EF
0x1801549d4  xor     r8d, r8d; pcbe
0x1801549d7  lea     rcx, ?WaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x1801549de  mov     rdx, rdi; pv
0x1801549e1  call    cs:__imp_CreateThreadpoolWait
0x1801549e7  mov     [rdi], rax
0x1801549ea  test    rax, rax
0x1801549ed  jnz     short loc_1801549FE
0x1801549ef  mov     rcx, rdi; this
0x1801549f2  mov     ebx, 80004005h
0x1801549f7  call    ?Cleanup@CRegistryWatcher@@AEAAXXZ; CRegistryWatcher::Cleanup(void)
0x1801549fc  jmp     short loc_180154A32
0x1801549fe  lea     rax, ?RegistryDeveloperModeChangedCallback@@YAX_NKPEAX@Z; RegistryDeveloperModeChangedCallback(bool,ulong,void *)
0x180154a05  mov     edx, 104h; unsigned __int64
0x180154a0a  mov     [rdi+8], rax
0x180154a0e  lea     rcx, [rdi+28h]; char *
0x180154a12  mov     rax, [rsp+38h+arg_30]
0x180154a17  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x180154a1e  mov     [rdi+10h], rax
0x180154a22  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180154a27  mov     rdx, [rdi]; struct _TP_WAIT *
0x180154a2a  mov     rcx, rdi; struct CRegistryWatcher *
0x180154a2d  call    ?WaitWorker@@YAXPEAVCRegistryWatcher@@PEAU_TP_WAIT@@@Z; WaitWorker(CRegistryWatcher *,_TP_WAIT *)
0x180154a32  mov     eax, ebx
0x180154a34  mov     rbx, [rsp+38h+arg_0]
0x180154a39  add     rsp, 30h
0x180154a3d  pop     rdi
0x180154a3e  retn
```
