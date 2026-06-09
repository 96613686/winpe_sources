# CreateTextServices

- ea: `0x180031ba0`
- end: `0x180031cb3`
- name: `CreateTextServices`
- size: `275`
- prototype: `__int64 __fastcall(struct IUnknown *, struct ITextHost2 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18005ff60`

## callees

- `0x180030568`
- `0x180031ba0`
- `0x18003f014`
- `0x180040e30`
- `0x180041c94`
- `0x18004d15c`
- `0x18005b600`
- `0x18005f754`
- `0x18005f95c`
- `0x18008f0a0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180031bc8`
- `KERNEL32!EnterCriticalSection` at `0x180031bc8`
- `KERNEL32!LeaveCriticalSection` at `0x180031c04`
- `KERNEL32!LeaveCriticalSection` at `0x180031c20`
- `KERNEL32!LeaveCriticalSection` at `0x180031c04`
- `KERNEL32!LeaveCriticalSection` at `0x180031c20`
- `KERNEL32!GetProcessHeap` at `0x180031c39`
- `KERNEL32!GetProcessHeap` at `0x180031c39`
- `KERNEL32!HeapAlloc` at `0x180031c59`
- `KERNEL32!HeapAlloc` at `0x180031c59`

## pseudocode

```c
__int64 __fastcall CreateTextServices(struct IUnknown *a1, struct ITextHost2 *a2, _QWORD *a3)
{
  HANDLE ProcessHeap; // rax
  CTxtEdit *v8; // rax
  CTxtEdit *v9; // rax
  const struct tagRECT *v10; // rdx
  CTxtEdit *v11; // rbx
  unsigned int v12; // edx

  if ( !byte_1800A4468 )
  {
    EnterCriticalSection(&g_CriticalSection);
    byte_1800A4468 = 1;
    CW32System::InitSysParams(0);
    CW32System::InitPreferredFontInfo();
    RegisterFETCs();
    if ( (int)CreateFormatCaches() < 0 || !(unsigned int)InitKinsokuClassify() )
    {
      LeaveCriticalSection(&g_CriticalSection);
      return 2147500037LL;
    }
    InitFontCache();
    LeaveCriticalSection(&g_CriticalSection);
  }
  if ( !a3 )
    return 2147942487LL;
  ProcessHeap = g_hHeap;
  if ( g_hHeap || (ProcessHeap = GetProcessHeap(), (g_hHeap = ProcessHeap) != 0) )
  {
    v8 = (CTxtEdit *)HeapAlloc(ProcessHeap, 8u, 0x138u);
    if ( v8 )
    {
      v9 = CTxtEdit::CTxtEdit(v8, a2, a1);
      v11 = v9;
      if ( v9 )
      {
        if ( (unsigned int)CTxtEdit::Init(v9, v10) )
        {
          *a3 = (char *)v11 + 232;
          return 0;
        }
        CTxtEdit::`scalar deleting destructor'(v11, v12);
        return 2147500037LL;
      }
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180031ba0  mov     [rsp+arg_0], rbx
0x180031ba5  mov     [rsp+arg_8], rsi
0x180031baa  push    rdi
0x180031bab  sub     rsp, 20h
0x180031baf  cmp     cs:byte_1800A4468, 0
0x180031bb6  mov     rdi, r8
0x180031bb9  mov     rbx, rdx
0x180031bbc  mov     rsi, rcx
0x180031bbf  jnz     short loc_180031C0A
0x180031bc1  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031bc8  call    cs:__imp_EnterCriticalSection
0x180031bce  xor     ecx, ecx; int
0x180031bd0  mov     cs:byte_1800A4468, 1
0x180031bd7  call    ?InitSysParams@CW32System@@SAXH@Z; CW32System::InitSysParams(int)
0x180031bdc  call    ?InitPreferredFontInfo@CW32System@@SAXXZ; CW32System::InitPreferredFontInfo(void)
0x180031be1  call    ?RegisterFETCs@@YAXXZ; RegisterFETCs(void)
0x180031be6  call    ?CreateFormatCaches@@YAJXZ; CreateFormatCaches(void)
0x180031beb  test    eax, eax
0x180031bed  js      short loc_180031C19
0x180031bef  call    ?InitKinsokuClassify@@YAHXZ; InitKinsokuClassify(void)
0x180031bf4  test    eax, eax
0x180031bf6  jz      short loc_180031C19
0x180031bf8  call    ?InitFontCache@@YAXXZ; InitFontCache(void)
0x180031bfd  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031c04  call    cs:__imp_LeaveCriticalSection
0x180031c0a  test    rdi, rdi
0x180031c0d  jnz     short loc_180031C2D
0x180031c0f  mov     eax, 80070057h
0x180031c14  jmp     loc_180031CA3
0x180031c19  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031c20  call    cs:__imp_LeaveCriticalSection
0x180031c26  mov     eax, 80004005h
0x180031c2b  jmp     short loc_180031CA3
0x180031c2d  mov     rax, cs:?g_hHeap@@3PEAXEA; void * g_hHeap
0x180031c34  test    rax, rax
0x180031c37  jnz     short loc_180031C4B
0x180031c39  call    cs:__imp_GetProcessHeap
0x180031c3f  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x180031c46  test    rax, rax
0x180031c49  jz      short loc_180031C9E
0x180031c4b  mov     edx, 8; dwFlags
0x180031c50  mov     r8d, 138h; dwBytes
0x180031c56  mov     rcx, rax; hHeap
0x180031c59  call    cs:__imp_HeapAlloc
0x180031c5f  test    rax, rax
0x180031c62  jz      short loc_180031C9E
0x180031c64  mov     r8, rsi; struct IUnknown *
0x180031c67  mov     rdx, rbx; struct ITextHost2 *
0x180031c6a  mov     rcx, rax; this
0x180031c6d  call    ??0CTxtEdit@@QEAA@PEAVITextHost2@@PEAUIUnknown@@@Z; CTxtEdit::CTxtEdit(ITextHost2 *,IUnknown *)
0x180031c72  mov     rbx, rax
0x180031c75  test    rax, rax
0x180031c78  jz      short loc_180031C9E
0x180031c7a  mov     rcx, rax; this
0x180031c7d  call    ?Init@CTxtEdit@@QEAAHPEBUtagRECT@@@Z; CTxtEdit::Init(tagRECT const *)
0x180031c82  test    eax, eax
0x180031c84  jz      short loc_180031C94
0x180031c86  lea     rax, [rbx+0E8h]
0x180031c8d  mov     [rdi], rax
0x180031c90  xor     eax, eax
0x180031c92  jmp     short loc_180031CA3
0x180031c94  mov     rcx, rbx; this
0x180031c97  call    ??_GCTxtEdit@@QEAAPEAXI@Z; CTxtEdit::`scalar deleting destructor'(uint)
0x180031c9c  jmp     short loc_180031C26
0x180031c9e  mov     eax, 8007000Eh
0x180031ca3  mov     rbx, [rsp+28h+arg_0]
0x180031ca8  mov     rsi, [rsp+28h+arg_8]
0x180031cad  add     rsp, 20h
0x180031cb1  pop     rdi
0x180031cb2  retn
```
