# DllGetClassObject

- ea: `0x180001270`
- end: `0x1800013b4`
- name: `DllGetClassObject`
- size: `324`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001270`
- `0x180007700`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000135e`
- `KERNEL32!LeaveCriticalSection` at `0x18000135e`
- `KERNEL32!EnterCriticalSection` at `0x180001320`
- `KERNEL32!EnterCriticalSection` at `0x180001320`
- `KERNEL32!EncodePointer` at `0x18000134e`
- `KERNEL32!EncodePointer` at `0x18000134e`
- `KERNEL32!DecodePointer` at `0x18000136c`
- `KERNEL32!DecodePointer` at `0x18000136c`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  _QWORD **v7; // rcx
  _QWORD *v8; // rsi
  _DWORD *v9; // rdx
  PVOID *v10; // rdi
  __int64 v11; // rcx
  __int64 (__fastcall ***v12)(PVOID, const IID *const, LPVOID *); // rax
  PVOID Ptr; // [rsp+20h] [rbp-28h] BYREF

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  if ( !ATL::_AtlComModule )
    return -2147418113;
  v7 = (_QWORD **)qword_18003EF70;
  v6 = 0;
  while ( 1 )
  {
    if ( v7 >= (_QWORD **)qword_18003EF78 )
      return -2147221231;
    v8 = *v7;
    if ( *v7 )
    {
      if ( v8[2] )
      {
        v9 = (_DWORD *)*v8;
        if ( rclsid->Data1 == *(_DWORD *)*v8
          && *(_DWORD *)&rclsid->Data2 == v9[1]
          && *(_DWORD *)rclsid->Data4 == v9[2]
          && *(_DWORD *)&rclsid->Data4[4] == v9[3] )
        {
          break;
        }
      }
    }
    ++v7;
  }
  v10 = (PVOID *)v8[4];
  if ( !*v10 )
  {
    EnterCriticalSection(&stru_18003EF80);
    if ( !*v10 )
    {
      v11 = v8[3];
      Ptr = 0;
      v6 = ((__int64 (__fastcall *)(__int64, GUID *, PVOID *))v8[2])(
             v11,
             &GUID_00000000_0000_0000_c000_000000000046,
             &Ptr);
      if ( v6 >= 0 )
        *v10 = EncodePointer(Ptr);
    }
    LeaveCriticalSection(&stru_18003EF80);
  }
  if ( *v10 )
  {
    v12 = (__int64 (__fastcall ***)(PVOID, const IID *const, LPVOID *))DecodePointer(*v10);
    v6 = (**v12)(v12, riid, ppv);
  }
  if ( !*ppv && !v6 )
    return -2147221231;
  return v6;
}

```

## disassembly

```asm
0x180001270  mov     [rsp+arg_0], rbx
0x180001275  mov     [rsp+arg_18], rbp
0x18000127a  push    rsi
0x18000127b  push    rdi
0x18000127c  push    r14
0x18000127e  sub     rsp, 30h
0x180001282  mov     rax, cs:__security_cookie
0x180001289  xor     rax, rsp
0x18000128c  mov     [rsp+48h+var_20], rax
0x180001291  mov     r14, r8
0x180001294  mov     rbp, rdx
0x180001297  mov     r9, rcx
0x18000129a  test    r8, r8
0x18000129d  jnz     short loc_1800012A9
0x18000129f  mov     ebx, 80004003h
0x1800012a4  jmp     loc_180001392
0x1800012a9  and     qword ptr [r8], 0
0x1800012ad  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800012b4  jnz     short loc_1800012C0
0x1800012b6  mov     ebx, 8000FFFFh
0x1800012bb  jmp     loc_180001392
0x1800012c0  mov     rcx, cs:qword_18003EF70
0x1800012c7  xor     ebx, ebx
0x1800012c9  mov     r8, cs:qword_18003EF78
0x1800012d0  jmp     short loc_180001309
0x1800012d2  mov     rsi, [rcx]
0x1800012d5  test    rsi, rsi
0x1800012d8  jz      short loc_180001305
0x1800012da  cmp     [rsi+10h], rbx
0x1800012de  jz      short loc_180001305
0x1800012e0  mov     rdx, [rsi]
0x1800012e3  mov     eax, [rdx]
0x1800012e5  cmp     [r9], eax
0x1800012e8  jnz     short loc_180001305
0x1800012ea  mov     eax, [rdx+4]
0x1800012ed  cmp     [r9+4], eax
0x1800012f1  jnz     short loc_180001305
0x1800012f3  mov     eax, [rdx+8]
0x1800012f6  cmp     [r9+8], eax
0x1800012fa  jnz     short loc_180001305
0x1800012fc  mov     eax, [rdx+0Ch]
0x1800012ff  cmp     [r9+0Ch], eax
0x180001303  jz      short loc_180001310
0x180001305  add     rcx, 8
0x180001309  cmp     rcx, r8
0x18000130c  jb      short loc_1800012D2
0x18000130e  jmp     short loc_18000138D
0x180001310  mov     rdi, [rsi+20h]
0x180001314  cmp     [rdi], rbx
0x180001317  jnz     short loc_180001364
0x180001319  lea     rcx, stru_18003EF80; lpCriticalSection
0x180001320  call    cs:__imp_EnterCriticalSection
0x180001326  cmp     [rdi], rbx
0x180001329  jnz     short loc_180001357
0x18000132b  mov     rcx, [rsi+18h]
0x18000132f  lea     r8, [rsp+48h+Ptr]
0x180001334  and     [rsp+48h+Ptr], rbx
0x180001339  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180001340  call    qword ptr [rsi+10h]
0x180001343  mov     ebx, eax
0x180001345  test    eax, eax
0x180001347  js      short loc_180001357
0x180001349  mov     rcx, [rsp+48h+Ptr]; Ptr
0x18000134e  call    cs:__imp_EncodePointer
0x180001354  mov     [rdi], rax
0x180001357  lea     rcx, stru_18003EF80; lpCriticalSection
0x18000135e  call    cs:__imp_LeaveCriticalSection
0x180001364  mov     rcx, [rdi]; Ptr
0x180001367  test    rcx, rcx
0x18000136a  jz      short loc_180001383
0x18000136c  call    cs:__imp_DecodePointer
0x180001372  mov     r8, r14
0x180001375  mov     rdx, rbp
0x180001378  mov     rcx, rax
0x18000137b  mov     r9, [rax]
0x18000137e  call    qword ptr [r9]
0x180001381  mov     ebx, eax
0x180001383  cmp     qword ptr [r14], 0
0x180001387  jnz     short loc_180001392
0x180001389  test    ebx, ebx
0x18000138b  jnz     short loc_180001392
0x18000138d  mov     ebx, 80040111h
0x180001392  mov     eax, ebx
0x180001394  mov     rcx, [rsp+48h+var_20]
0x180001399  xor     rcx, rsp; StackCookie
0x18000139c  call    __security_check_cookie
0x1800013a1  mov     rbx, [rsp+48h+arg_0]
0x1800013a6  mov     rbp, [rsp+48h+arg_18]
0x1800013ab  add     rsp, 30h
0x1800013af  pop     r14
0x1800013b1  pop     rdi
0x1800013b2  pop     rsi
0x1800013b3  retn
```
