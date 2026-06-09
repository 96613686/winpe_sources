# OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)

- ea: `0x18001441c`
- end: `0x18001453e`
- name: `?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z`
- size: `290`
- prototype: `__int64 __fastcall(struct CCredentials *this, unsigned __int16 *, unsigned __int16 *, unsigned int, struct IMSAdminBaseW **, unsigned int *)`
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x180003dbc`
- `0x1800049c0`
- `0x180005830`
- `0x180005a00`
- `0x180005cd0`
- `0x180006090`
- `0x180006240`
- `0x180006660`
- `0x180006894`
- `0x1800085a0`
- `0x18000a164`
- `0x18000a860`
- `0x18000aa70`
- `0x18000ad88`
- `0x18000b2b0`
- `0x18000d83c`
- `0x180015664`

## callees

- `0x180013430`
- `0x18001441c`
- `0x180014624`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall OpenAdminBaseKey(
        struct CCredentials *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IMSAdminBaseW **a5,
        unsigned int *a6)
{
  struct IMSAdminBaseW **v6; // r12
  struct IMSAdminBaseW *v9; // rdi
  int v12; // eax
  int inited; // ebx
  struct IMSAdminBaseW *v15; // [rsp+40h] [rbp-48h] BYREF

  v6 = a5;
  LODWORD(a5) = 0;
  v9 = *v6;
  v12 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD))(*v6)->lpVtbl->OpenKey)(*v6, 0);
  inited = v12;
  if ( v12 >= 0
    || ((unsigned __int16)v12 == 1722 || (unsigned int)(unsigned __int16)v12 - 1725 <= 2 || v12 == -2147417848)
    && (v15 = 0, inited = InitAdminBase(this, a2, &v15), inited >= 0)
    && (UninitAdminBase(v9),
        v9 = v15,
        *v6 = v15,
        inited = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, unsigned __int16 *, _QWORD, int, struct IMSAdminBaseW ***))v9->lpVtbl->OpenKey)(
                   v9,
                   0,
                   a3,
                   a4,
                   30000,
                   &a5),
        inited >= 0) )
  {
    *a6 = (unsigned int)a5;
  }
  else if ( (_DWORD)a5 )
  {
    ((void (__fastcall *)(struct IMSAdminBaseW *))v9->lpVtbl->CloseKey)(v9);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001441c  mov     r11, rsp
0x18001441f  push    rbx
0x180014420  push    rbp
0x180014421  push    rsi
0x180014422  push    rdi
0x180014423  push    r12
0x180014425  push    r14
0x180014427  push    r15
0x180014429  sub     rsp, 50h
0x18001442d  mov     r12, [rsp+88h+arg_20]
0x180014435  mov     rbp, rcx
0x180014438  lea     rcx, [r11+28h]
0x18001443c  mov     dword ptr [r11+28h], 0
0x180014444  mov     [r11-60h], rcx
0x180014448  mov     rsi, rdx
0x18001444b  xor     edx, edx
0x18001444d  mov     [rsp+88h+var_68], 7530h
0x180014455  mov     rdi, [r12]
0x180014459  mov     r14d, r9d
0x18001445c  mov     rcx, rdi
0x18001445f  mov     r15, r8
0x180014462  mov     rax, [rdi]
0x180014465  mov     rax, [rax+88h]
0x18001446c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014471  mov     ebx, eax
0x180014473  test    eax, eax
0x180014475  jns     loc_18001451C
0x18001447b  movzx   ecx, ax
0x18001447e  cmp     ecx, 6BAh
0x180014484  jz      short loc_180014498
0x180014486  add     ecx, 0FFFFF943h
0x18001448c  cmp     ecx, 2
0x18001448f  jbe     short loc_180014498
0x180014491  cmp     eax, 80010108h
0x180014496  jnz     short loc_1800144FD
0x180014498  lea     r8, [rsp+88h+var_48]; struct IMSAdminBaseW **
0x18001449d  mov     [rsp+88h+var_48], 0
0x1800144a6  mov     rdx, rsi; unsigned __int16 *
0x1800144a9  mov     rcx, rbp; this
0x1800144ac  call    ?InitAdminBase@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@@Z; InitAdminBase(CCredentials &,ushort const *,IMSAdminBaseW * *)
0x1800144b1  mov     ebx, eax
0x1800144b3  test    eax, eax
0x1800144b5  js      short loc_1800144FD
0x1800144b7  mov     rcx, rdi; struct IMSAdminBaseW *
0x1800144ba  call    ?UninitAdminBase@@YAXPEAUIMSAdminBaseW@@@Z; UninitAdminBase(IMSAdminBaseW *)
0x1800144bf  mov     rdi, [rsp+88h+var_48]
0x1800144c4  lea     rcx, [rsp+88h+arg_20]
0x1800144cc  mov     [rsp+88h+var_60], rcx
0x1800144d1  mov     r9d, r14d
0x1800144d4  mov     [r12], rdi
0x1800144d8  mov     r8, r15
0x1800144db  xor     edx, edx
0x1800144dd  mov     [rsp+88h+var_68], 7530h
0x1800144e5  mov     rax, [rdi]
0x1800144e8  mov     rcx, rdi
0x1800144eb  mov     rax, [rax+88h]
0x1800144f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144f7  mov     ebx, eax
0x1800144f9  test    eax, eax
0x1800144fb  jns     short loc_18001451C
0x1800144fd  mov     edx, dword ptr [rsp+88h+arg_20]
0x180014504  test    edx, edx
0x180014506  jz      short loc_18001452D
0x180014508  mov     rax, [rdi]
0x18001450b  mov     rcx, rdi
0x18001450e  mov     rax, [rax+90h]
0x180014515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001451a  jmp     short loc_18001452D
0x18001451c  mov     rcx, [rsp+88h+arg_28]
0x180014524  mov     eax, dword ptr [rsp+88h+arg_20]
0x18001452b  mov     [rcx], eax
0x18001452d  mov     eax, ebx
0x18001452f  add     rsp, 50h
0x180014533  pop     r15
0x180014535  pop     r14
0x180014537  pop     r12
0x180014539  pop     rdi
0x18001453a  pop     rsi
0x18001453b  pop     rbp
0x18001453c  pop     rbx
0x18001453d  retn
```
