# REQUEST_OBJECT::SerializeText(ushort *,ulong)

- ea: `0x18001faa0`
- end: `0x18001fcab`
- name: `?SerializeText@REQUEST_OBJECT@@UEAAJPEAGK@Z`
- size: `523`
- prototype: `int(REQUEST_OBJECT *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d654`
- `0x18001faa0`
- `0x180034cca`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc8b`

## pseudocode

```c
__int64 __fastcall REQUEST_OBJECT::SerializeText(REQUEST_OBJECT *this, unsigned __int16 *a2, unsigned int a3)
{
  __int64 v4; // rcx
  int v7; // ebx
  __int64 v8; // rbx
  int v9; // eax
  wchar_t *v10; // rcx
  int v12; // [rsp+38h] [rbp-11h]
  LPVOID v13; // [rsp+60h] [rbp+17h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v15; // [rsp+70h] [rbp+27h] BYREF
  __int64 v16; // [rsp+78h] [rbp+2Fh] BYREF
  __int64 v17; // [rsp+80h] [rbp+37h] BYREF
  int v18; // [rsp+B0h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp+7Fh] BYREF

  v13 = 0;
  v4 = *((_QWORD *)this + 27);
  pv = 0;
  String1 = 0;
  v18 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 24LL))(v4, &v17);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 27) + 48LL))(*((_QWORD *)this + 27), &pv);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 27) + 40LL))(*((_QWORD *)this + 27), &v13);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(**((_QWORD **)this + 27) + 80LL))(
               *((_QWORD *)this + 27),
               &String1);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 27) + 88LL))(
                 *((_QWORD *)this + 27),
                 &v18);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(REQUEST_OBJECT *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this
                                                                                                  + 80LL))(
                   this,
                   L"Stage",
                   &v15);
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(REQUEST_OBJECT *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this + 80LL))(
                     this,
                     L"Module",
                     &v16);
              if ( v7 >= 0 )
              {
                v8 = v15;
                v9 = wcscmp_0(String1, L"::1");
                v10 = L"localhost";
                if ( v9 )
                  v10 = String1;
                v12 = v18;
                v7 = StringCchPrintfW(
                       a2,
                       a3,
                       L"%ws \"%ws\" (url:%ws %ws, time:%d msec, client:%ws, stage:%ws, module:%ws)",
                       L"REQUEST",
                       v17,
                       v13,
                       pv,
                       v12,
                       v10,
                       v8,
                       v16);
              }
            }
          }
        }
      }
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v13 )
  {
    CoTaskMemFree(v13);
    v13 = 0;
  }
  if ( String1 )
    CoTaskMemFree(String1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001faa0  mov     [rsp-8+arg_8], rbx
0x18001faa5  mov     [rsp-8+arg_10], rsi
0x18001faaa  push    rbp
0x18001faab  push    rdi
0x18001faac  push    r14
0x18001faae  lea     rbp, [rsp-47h]
0x18001fab3  sub     rsp, 90h
0x18001faba  mov     rdi, rcx
0x18001fabd  mov     [rbp+57h+var_40], 0
0x18001fac5  mov     rcx, [rcx+0D8h]
0x18001facc  mov     r14, rdx
0x18001facf  mov     [rbp+57h+pv], 0
0x18001fad7  lea     rdx, [rbp+57h+var_20]
0x18001fadb  mov     [rbp+57h+String1], 0
0x18001fae3  mov     [rbp+57h+arg_0], 0
0x18001faea  mov     [rbp+57h+var_28], 0
0x18001faf2  mov     [rbp+57h+var_30], 0
0x18001fafa  mov     [rbp+57h+var_20], 0
0x18001fb02  mov     rax, [rcx]
0x18001fb05  mov     esi, r8d
0x18001fb08  mov     rax, [rax+18h]
0x18001fb0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb11  mov     ebx, eax
0x18001fb13  test    eax, eax
0x18001fb15  js      loc_18001FC54
0x18001fb1b  mov     rcx, [rdi+0D8h]
0x18001fb22  lea     rdx, [rbp+57h+pv]
0x18001fb26  mov     rax, [rcx]
0x18001fb29  mov     rax, [rax+30h]
0x18001fb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb32  mov     ebx, eax
0x18001fb34  test    eax, eax
0x18001fb36  js      loc_18001FC54
0x18001fb3c  mov     rcx, [rdi+0D8h]
0x18001fb43  lea     rdx, [rbp+57h+var_40]
0x18001fb47  mov     rax, [rcx]
0x18001fb4a  mov     rax, [rax+28h]
0x18001fb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb53  mov     ebx, eax
0x18001fb55  test    eax, eax
0x18001fb57  js      loc_18001FC54
0x18001fb5d  mov     rcx, [rdi+0D8h]
0x18001fb64  lea     rdx, [rbp+57h+String1]
0x18001fb68  mov     rax, [rcx]
0x18001fb6b  mov     rax, [rax+50h]
0x18001fb6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb74  mov     ebx, eax
0x18001fb76  test    eax, eax
0x18001fb78  js      loc_18001FC54
0x18001fb7e  mov     rcx, [rdi+0D8h]
0x18001fb85  lea     rdx, [rbp+57h+arg_0]
0x18001fb89  mov     rax, [rcx]
0x18001fb8c  mov     rax, [rax+58h]
0x18001fb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb95  mov     ebx, eax
0x18001fb97  test    eax, eax
0x18001fb99  js      loc_18001FC54
0x18001fb9f  mov     rax, [rdi]
0x18001fba2  lea     r8, [rbp+57h+var_30]
0x18001fba6  lea     rdx, aStage; "Stage"
0x18001fbad  mov     rcx, rdi
0x18001fbb0  mov     rax, [rax+50h]
0x18001fbb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbb9  mov     ebx, eax
0x18001fbbb  test    eax, eax
0x18001fbbd  js      loc_18001FC54
0x18001fbc3  mov     rax, [rdi]
0x18001fbc6  lea     r8, [rbp+57h+var_28]
0x18001fbca  lea     rdx, aModule; "Module"
0x18001fbd1  mov     rcx, rdi
0x18001fbd4  mov     rax, [rax+50h]
0x18001fbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbdd  mov     ebx, eax
0x18001fbdf  test    eax, eax
0x18001fbe1  js      short loc_18001FC54
0x18001fbe3  mov     rcx, [rbp+57h+String1]; String1
0x18001fbe7  lea     rdx, a1; "::1"
0x18001fbee  mov     rbx, [rbp+57h+var_30]
0x18001fbf2  call    wcscmp_0
0x18001fbf7  test    eax, eax
0x18001fbf9  lea     rcx, aLocalhost; "localhost"
0x18001fc00  mov     rax, [rbp+57h+var_28]
0x18001fc04  lea     r9, aRequest; "REQUEST"
0x18001fc0b  cmovnz  rcx, [rbp+57h+String1]
0x18001fc10  lea     r8, aWsWsUrlWsWsTim; "%ws \"%ws\" (url:%ws %ws, time:%d msec,"...
0x18001fc17  mov     [rsp+0A0h+var_50], rax
0x18001fc1c  mov     edx, esi; unsigned __int64
0x18001fc1e  mov     eax, [rbp+57h+arg_0]
0x18001fc21  mov     [rsp+0A0h+var_58], rbx
0x18001fc26  mov     [rsp+0A0h+var_60], rcx
0x18001fc2b  mov     rcx, r14; unsigned __int16 *
0x18001fc2e  mov     [rsp+0A0h+var_68], eax
0x18001fc32  mov     rax, [rbp+57h+pv]
0x18001fc36  mov     [rsp+0A0h+var_70], rax
0x18001fc3b  mov     rax, [rbp+57h+var_40]
0x18001fc3f  mov     [rsp+0A0h+var_78], rax
0x18001fc44  mov     rax, [rbp+57h+var_20]
0x18001fc48  mov     [rsp+0A0h+var_80], rax
0x18001fc4d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fc52  mov     ebx, eax
0x18001fc54  mov     rcx, [rbp+57h+pv]; pv
0x18001fc58  test    rcx, rcx
0x18001fc5b  jz      short loc_18001FC6B
0x18001fc5d  call    cs:__imp_CoTaskMemFree
0x18001fc63  mov     [rbp+57h+pv], 0
0x18001fc6b  mov     rcx, [rbp+57h+var_40]; pv
0x18001fc6f  test    rcx, rcx
0x18001fc72  jz      short loc_18001FC82
0x18001fc74  call    cs:__imp_CoTaskMemFree
0x18001fc7a  mov     [rbp+57h+var_40], 0
0x18001fc82  mov     rcx, [rbp+57h+String1]; pv
0x18001fc86  test    rcx, rcx
0x18001fc89  jz      short loc_18001FC91
0x18001fc8b  call    cs:__imp_CoTaskMemFree
0x18001fc91  lea     r11, [rsp+0A0h+var_10]
0x18001fc99  mov     eax, ebx
0x18001fc9b  mov     rbx, [r11+28h]
0x18001fc9f  mov     rsi, [r11+30h]
0x18001fca3  mov     rsp, r11
0x18001fca6  pop     r14
0x18001fca8  pop     rdi
0x18001fca9  pop     rbp
0x18001fcaa  retn
```
