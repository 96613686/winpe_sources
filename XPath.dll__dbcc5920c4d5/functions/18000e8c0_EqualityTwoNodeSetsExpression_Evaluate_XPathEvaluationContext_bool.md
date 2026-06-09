# EqualityTwoNodeSetsExpression::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x18000e8c0`
- end: `0x18000ea98`
- name: `?Evaluate@EqualityTwoNodeSetsExpression@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `472`
- prototype: `int(EqualityTwoNodeSetsExpression *__hidden this, struct XPathEvaluationContext *, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000e77c`
- `0x18000e7bc`
- `0x18000e8c0`
- `0x18000ee14`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e8fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e92a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e8fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e92a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e918`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e918`

## pseudocode

```c
__int64 __fastcall EqualityTwoNodeSetsExpression::Evaluate(
        EqualityTwoNodeSetsExpression *this,
        struct XPathEvaluationContext *a2,
        bool *a3)
{
  HANDLE ProcessHeap; // rax
  HANDLE v7; // rax
  __int64 v8; // rcx
  int v9; // ebx
  int v10; // eax
  __int64 (*i)(void); // rax
  int v12; // eax
  int v13; // edi
  char v14; // bl
  struct XPathNavigatorInternal *v15; // rax
  char v16; // bl
  struct XPathNavigatorInternal *v17; // rax
  _BYTE v19[8]; // [rsp+30h] [rbp-40h] BYREF
  LPVOID v20; // [rsp+38h] [rbp-38h]
  int v21; // [rsp+40h] [rbp-30h]
  _BYTE v22[8]; // [rsp+50h] [rbp-20h] BYREF
  LPVOID v23; // [rsp+58h] [rbp-18h]
  int v24; // [rsp+60h] [rbp-10h]

  StringTable::StringTable((StringTable *)v22);
  StringTable::StringTable((StringTable *)v19);
  ProcessHeap = GetProcessHeap();
  v23 = HeapAlloc(ProcessHeap, 8u, 0x200u);
  if ( v23 && (v24 = 64, v7 = GetProcessHeap(), (v20 = HeapAlloc(v7, 8u, 0x200u)) != 0) )
  {
    v8 = *((_QWORD *)this + 3);
    v21 = 64;
    v9 = (*(__int64 (__fastcall **)(__int64, struct XPathEvaluationContext *))(*(_QWORD *)v8 + 96LL))(v8, a2);
    if ( v9 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *))(**((_QWORD **)this + 4) + 96LL))(
              *((_QWORD *)this + 4),
              a2);
      if ( v10 >= 0 )
      {
        *a3 = 0;
        v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
        for ( i = *(__int64 (**)(void))(**((_QWORD **)this + 4) + 48LL);
              ;
              i = *(__int64 (**)(void))(**((_QWORD **)this + 4) + 48LL) )
        {
          v12 = i();
          v13 = v12;
          if ( v9 == 1 && v12 == 1 )
          {
            StringTable::~StringTable((StringTable *)v19);
            StringTable::~StringTable((StringTable *)v22);
            return 0;
          }
          if ( v9 < 0 )
            goto LABEL_21;
          if ( v12 < 0 )
            break;
          if ( v9 != 1 )
          {
            v14 = *((_BYTE *)this + 16);
            v15 = (struct XPathNavigatorInternal *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 72LL))(*((_QWORD *)this + 3));
            v10 = EqualityTwoNodeSetsExpression::ProcessNavigation(
                    v15,
                    v14,
                    (struct StringTable *)v22,
                    (struct StringTable *)v19,
                    a3);
            if ( v10 < 0 || *a3 )
              goto LABEL_5;
          }
          if ( v13 != 1 )
          {
            v16 = *((_BYTE *)this + 16);
            v17 = (struct XPathNavigatorInternal *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 72LL))(*((_QWORD *)this + 4));
            v9 = EqualityTwoNodeSetsExpression::ProcessNavigation(
                   v17,
                   v16,
                   (struct StringTable *)v19,
                   (struct StringTable *)v22,
                   a3);
            if ( v9 < 0 || *a3 )
              goto LABEL_21;
          }
          v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3));
        }
        v9 = v12;
      }
      else
      {
LABEL_5:
        v9 = v10;
      }
    }
  }
  else
  {
    v9 = -2147024888;
  }
LABEL_21:
  StringTable::~StringTable((StringTable *)v19);
  StringTable::~StringTable((StringTable *)v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e8c0  push    rbp
0x18000e8c2  push    rbx
0x18000e8c3  push    rsi
0x18000e8c4  push    rdi
0x18000e8c5  push    r14
0x18000e8c7  mov     rbp, rsp
0x18000e8ca  sub     rsp, 70h
0x18000e8ce  mov     rsi, rcx
0x18000e8d1  mov     r14, r8
0x18000e8d4  lea     rcx, [rbp+var_20]; this
0x18000e8d8  mov     rdi, rdx
0x18000e8db  call    ??0StringTable@@QEAA@XZ; StringTable::StringTable(void)
0x18000e8e0  lea     rcx, [rbp+var_40]; this
0x18000e8e4  call    ??0StringTable@@QEAA@XZ; StringTable::StringTable(void)
0x18000e8e9  call    cs:__imp_GetProcessHeap
0x18000e8ef  mov     edx, 8; dwFlags
0x18000e8f4  mov     r8d, 200h; dwBytes
0x18000e8fa  mov     rcx, rax; hHeap
0x18000e8fd  call    cs:__imp_HeapAlloc
0x18000e903  mov     [rbp+var_18], rax
0x18000e907  test    rax, rax
0x18000e90a  jz      loc_18000EA74
0x18000e910  mov     ebx, 40h ; '@'
0x18000e915  mov     [rbp+var_10], ebx
0x18000e918  call    cs:__imp_GetProcessHeap
0x18000e91e  lea     edx, [rbx-38h]; dwFlags
0x18000e921  mov     r8d, 200h; dwBytes
0x18000e927  mov     rcx, rax; hHeap
0x18000e92a  call    cs:__imp_HeapAlloc
0x18000e930  mov     [rbp+var_38], rax
0x18000e934  test    rax, rax
0x18000e937  jz      loc_18000EA74
0x18000e93d  mov     rcx, [rsi+18h]
0x18000e941  mov     rdx, rdi
0x18000e944  mov     [rbp+var_30], ebx
0x18000e947  mov     rax, [rcx]
0x18000e94a  mov     rax, [rax+60h]
0x18000e94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e953  mov     ebx, eax
0x18000e955  test    eax, eax
0x18000e957  js      loc_18000EA79
0x18000e95d  mov     rcx, [rsi+20h]
0x18000e961  mov     rdx, rdi
0x18000e964  mov     rax, [rcx]
0x18000e967  mov     rax, [rax+60h]
0x18000e96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e970  test    eax, eax
0x18000e972  jns     short loc_18000E97B
0x18000e974  mov     ebx, eax
0x18000e976  jmp     loc_18000EA79
0x18000e97b  mov     byte ptr [r14], 0
0x18000e97f  mov     rcx, [rsi+18h]
0x18000e983  mov     rax, [rcx]
0x18000e986  mov     rax, [rax+30h]
0x18000e98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e98f  mov     rcx, [rsi+20h]
0x18000e993  mov     ebx, eax
0x18000e995  mov     rdx, [rcx]
0x18000e998  mov     rax, [rdx+30h]
0x18000e99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9a1  mov     edi, eax
0x18000e9a3  cmp     ebx, 1
0x18000e9a6  jnz     short loc_18000E9B0
0x18000e9a8  cmp     eax, ebx
0x18000e9aa  jz      loc_18000EA5A
0x18000e9b0  test    ebx, ebx
0x18000e9b2  js      loc_18000EA79
0x18000e9b8  test    edi, edi
0x18000e9ba  js      loc_18000EA70
0x18000e9c0  cmp     ebx, 1
0x18000e9c3  jz      short loc_18000E9FD
0x18000e9c5  mov     rcx, [rsi+18h]
0x18000e9c9  mov     bl, [rsi+10h]
0x18000e9cc  mov     rax, [rcx]
0x18000e9cf  mov     rax, [rax+48h]
0x18000e9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d8  lea     r9, [rbp+var_40]; struct StringTable *
0x18000e9dc  mov     [rsp+70h+var_50], r14; bool *
0x18000e9e1  lea     r8, [rbp+var_20]; struct StringTable *
0x18000e9e5  mov     dl, bl; bool
0x18000e9e7  mov     rcx, rax; struct XPathNavigatorInternal *
0x18000e9ea  call    ?ProcessNavigation@EqualityTwoNodeSetsExpression@@CAJAEAVXPathNavigatorInternal@@_NAEAVStringTable@@2AEA_N@Z; EqualityTwoNodeSetsExpression::ProcessNavigation(XPathNavigatorInternal &,bool,StringTable &,StringTable &,bool &)
0x18000e9ef  test    eax, eax
0x18000e9f1  js      short loc_18000E974
0x18000e9f3  cmp     byte ptr [r14], 0
0x18000e9f7  jnz     loc_18000E974
0x18000e9fd  cmp     edi, 1
0x18000ea00  jz      short loc_18000EA38
0x18000ea02  mov     rcx, [rsi+20h]
0x18000ea06  mov     bl, [rsi+10h]
0x18000ea09  mov     rax, [rcx]
0x18000ea0c  mov     rax, [rax+48h]
0x18000ea10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea15  lea     r9, [rbp+var_20]; struct StringTable *
0x18000ea19  mov     [rsp+70h+var_50], r14; bool *
0x18000ea1e  lea     r8, [rbp+var_40]; struct StringTable *
0x18000ea22  mov     dl, bl; bool
0x18000ea24  mov     rcx, rax; struct XPathNavigatorInternal *
0x18000ea27  call    ?ProcessNavigation@EqualityTwoNodeSetsExpression@@CAJAEAVXPathNavigatorInternal@@_NAEAVStringTable@@2AEA_N@Z; EqualityTwoNodeSetsExpression::ProcessNavigation(XPathNavigatorInternal &,bool,StringTable &,StringTable &,bool &)
0x18000ea2c  mov     ebx, eax
0x18000ea2e  test    eax, eax
0x18000ea30  js      short loc_18000EA79
0x18000ea32  cmp     byte ptr [r14], 0
0x18000ea36  jnz     short loc_18000EA79
0x18000ea38  mov     rcx, [rsi+18h]
0x18000ea3c  mov     rax, [rcx]
0x18000ea3f  mov     rax, [rax+30h]
0x18000ea43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea48  mov     rcx, [rsi+20h]
0x18000ea4c  mov     ebx, eax
0x18000ea4e  mov     rax, [rcx]
0x18000ea51  mov     rax, [rax+30h]
0x18000ea55  jmp     loc_18000E99C
0x18000ea5a  lea     rcx, [rbp+var_40]; this
0x18000ea5e  call    ??1StringTable@@UEAA@XZ; StringTable::~StringTable(void)
0x18000ea63  lea     rcx, [rbp+var_20]; this
0x18000ea67  call    ??1StringTable@@UEAA@XZ; StringTable::~StringTable(void)
0x18000ea6c  xor     eax, eax
0x18000ea6e  jmp     short loc_18000EA8D
0x18000ea70  mov     ebx, edi
0x18000ea72  jmp     short loc_18000EA79
0x18000ea74  mov     ebx, 80070008h
0x18000ea79  lea     rcx, [rbp+var_40]; this
0x18000ea7d  call    ??1StringTable@@UEAA@XZ; StringTable::~StringTable(void)
0x18000ea82  lea     rcx, [rbp+var_20]; this
0x18000ea86  call    ??1StringTable@@UEAA@XZ; StringTable::~StringTable(void)
0x18000ea8b  mov     eax, ebx
0x18000ea8d  add     rsp, 70h
0x18000ea91  pop     r14
0x18000ea93  pop     rdi
0x18000ea94  pop     rsi
0x18000ea95  pop     rbx
0x18000ea96  pop     rbp
0x18000ea97  retn
```
