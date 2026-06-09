# Ivy::Extras::Interactivities::RegisterWin32Control(ID2D1Factory &,IDWriteFactory &)

- ea: `0x180164210`
- end: `0x180164378`
- name: `?RegisterWin32Control@Interactivities@Extras@Ivy@@YA_NAEAUID2D1Factory@@AEAUIDWriteFactory@@@Z`
- size: `360`
- prototype: `bool __fastcall(Ivy::Extras::Interactivities *__hidden this, struct ID2D1Factory *, struct IDWriteFactory *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180011ac4`
- `0x180029294`
- `0x180164210`
- `0x18016577c`
- `0x180165a80`
- `0x18016d76e`
- `0x18016eaf0`

## import_xrefs

- `USER32!LoadCursorW` at `0x1801642a9`
- `USER32!LoadCursorW` at `0x1801642a9`

## string_xrefs

- `0x180164369`: `RegisterWin32Control() already called.`

## pseudocode

```c
char __fastcall Ivy::Extras::Interactivities::RegisterWin32Control(
        Ivy::Extras::Interactivities *this,
        struct ID2D1Factory *a2,
        struct IDWriteFactory *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  Ivy::Extras *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  WNDCLASSEXW v12; // [rsp+30h] [rbp-58h] BYREF

  if ( _InterlockedIncrement(&dword_18022FF38) != 1 )
    return 1;
  memset(&v12, 0, sizeof(v12));
  if ( (unsigned int)sub_180165A80(v7, v6, &v12) )
  {
    sub_180029294(508641728);
    try
    {
      sub_180011AC4(508641728, "RegisterWin32Control() already called.");
    }
    catch ( ... )
    {
      v10 = sub_180001030();
      if ( *(_QWORD *)(v10 + 80) )
      {
        if ( *(_DWORD *)(v10 + 88) <= 3u )
        {
          v11 = sub_180001030();
          if ( *(_QWORD *)(v11 + 80) )
            (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64, __int64 *))(**(_QWORD **)(v11 + 80) + 16LL))(
              *(_QWORD *)(v11 + 80),
              3,
              1,
              508641699,
              &qword_1801AB2B8);
        }
      }
      return 0;
    }
  }
  v12.cbSize = 80;
  v12.style = 3;
  v12.lpfnWndProc = (WNDPROC)sub_180164470;
  v12.cbClsExtra = 0;
  v12.cbWndExtra = 8;
  v12.hInstance = 0;
  v12.hIcon = 0;
  v12.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  *(_OWORD *)&v12.hbrBackground = 0;
  v12.lpszClassName = L"IvyChartControl";
  v12.hIconSm = 0;
  sub_18016577C(&v12);
  if ( this )
    (*(void (__fastcall **)(Ivy::Extras::Interactivities *))(*(_QWORD *)this + 8LL))(this);
  v8 = qword_1802300F0;
  qword_1802300F0 = (__int64)this;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( a2 )
    (*(void (__fastcall **)(struct ID2D1Factory *))(*(_QWORD *)a2 + 8LL))(a2);
  v9 = qword_1802300F8;
  qword_1802300F8 = a2;
  if ( v9 )
    (*(void (__fastcall **)(Ivy::Extras *))(*(_QWORD *)v9 + 16LL))(v9);
  return 1;
}

```

## disassembly

```asm
0x180164210  mov     [rsp+arg_0], rbx
0x180164215  push    rdi
0x180164216  sub     rsp, 80h
0x18016421d  mov     rbx, rdx
0x180164220  mov     rdi, rcx
0x180164223  mov     r8d, 1
0x180164229  lock xadd cs:dword_18022FF38, r8d
0x180164232  inc     r8d
0x180164235  cmp     r8d, 1
0x180164239  jz      short loc_180164242
0x18016423b  mov     al, 1
0x18016423d  jmp     loc_18016434C
0x180164242  xor     edx, edx; Val
0x180164244  lea     r8d, [rdx+50h]; Size
0x180164248  lea     rcx, [rsp+88h+var_58]; void *
0x18016424d  call    memset
0x180164252  lea     r8, [rsp+88h+var_58]
0x180164257  call    sub_180165A80
0x18016425c  test    eax, eax
0x18016425e  jnz     loc_18016435D
0x180164264  mov     [rsp+88h+var_58.cbSize], 50h ; 'P'
0x18016426c  mov     [rsp+88h+var_58.style], 3
0x180164274  lea     rax, sub_180164470
0x18016427b  mov     [rsp+88h+var_58.lpfnWndProc], rax
0x180164280  mov     [rsp+88h+var_58.cbClsExtra], 0
0x180164288  mov     [rsp+88h+var_58.cbWndExtra], 8
0x180164290  mov     [rsp+88h+var_58.hInstance], 0
0x180164299  mov     [rsp+88h+var_58.hIcon], 0
0x1801642a2  mov     edx, 7F00h; lpCursorName
0x1801642a7  xor     ecx, ecx; hInstance
0x1801642a9  call    cs:LoadCursorW
0x1801642af  mov     [rsp+88h+var_58.hCursor], rax
0x1801642b4  xorps   xmm0, xmm0
0x1801642b7  movdqa  xmmword ptr [rsp+88h+var_58.hbrBackground], xmm0
0x1801642bd  lea     rax, szClass; "IvyChartControl"
0x1801642c4  mov     [rsp+88h+var_58.lpszClassName], rax
0x1801642c9  mov     [rsp+88h+var_58.hIconSm], 0
0x1801642d2  lea     rcx, [rsp+88h+var_58]; WNDCLASSEXW *
0x1801642d7  call    sub_18016577C
0x1801642dc  test    rdi, rdi
0x1801642df  jz      short loc_1801642F1
0x1801642e1  mov     rax, [rdi]
0x1801642e4  mov     rcx, rdi
0x1801642e7  mov     rax, [rax+8]
0x1801642eb  call    cs:__guard_dispatch_icall_fptr
0x1801642f1  mov     rcx, cs:qword_1802300F0
0x1801642f8  mov     cs:qword_1802300F0, rdi
0x1801642ff  test    rcx, rcx
0x180164302  jz      short loc_180164311
0x180164304  mov     rax, [rcx]
0x180164307  mov     rax, [rax+10h]
0x18016430b  call    cs:__guard_dispatch_icall_fptr
0x180164311  test    rbx, rbx
0x180164314  jz      short loc_180164326
0x180164316  mov     rax, [rbx]
0x180164319  mov     rcx, rbx
0x18016431c  mov     rax, [rax+8]
0x180164320  call    cs:__guard_dispatch_icall_fptr
0x180164326  mov     rcx, cs:qword_1802300F8
0x18016432d  mov     cs:qword_1802300F8, rbx
0x180164334  test    rcx, rcx
0x180164337  jz      short loc_180164346
0x180164339  mov     rax, [rcx]
0x18016433c  mov     rax, [rax+10h]
0x180164340  call    cs:__guard_dispatch_icall_fptr
0x180164346  mov     al, 1
0x180164348  jmp     short loc_18016434C
0x18016434a  xor     al, al
0x18016434c  mov     rbx, [rsp+88h+arg_0]
0x180164354  add     rsp, 80h
0x18016435b  pop     rdi
0x18016435c  retn
0x18016435d  mov     ebx, 1E5141C0h
0x180164362  mov     ecx, ebx
0x180164364  call    sub_180029294
0x180164369  lea     rdx, aRegisterwin32c_0; "RegisterWin32Control() already called."
0x180164370  mov     ecx, ebx
0x180164372  call    sub_180011AC4
```
