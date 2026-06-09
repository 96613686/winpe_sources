# CGuestAudioFormatEnumerator::GetFormat(uint,tWAVEFORMATEX * *)

- ea: `0x180100eb0`
- end: `0x180101018`
- name: `?GetFormat@CGuestAudioFormatEnumerator@@UEAAJIPEAPEAUtWAVEFORMATEX@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(CGuestAudioFormatEnumerator *__hidden this, unsigned int, struct tWAVEFORMATEX **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010a90`
- `0x18004d8a8`
- `0x1800fec40`
- `0x180100eb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180100fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180100fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100fbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100fbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100ffb`

## pseudocode

```c
__int64 __fastcall CGuestAudioFormatEnumerator::GetFormat(
        CGuestAudioFormatEnumerator *this,
        int a2,
        struct tWAVEFORMATEX **a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // edx
  int v7; // edi
  void *v8; // rcx
  struct tWAVEFORMATEX *v10; // rax
  __int64 v11; // rcx
  void *v12; // rcx
  int v13; // [rsp+20h] [rbp-79h]
  int v14; // [rsp+20h] [rbp-79h]
  int v15[2]; // [rsp+30h] [rbp-69h] BYREF
  LPVOID *p_pv; // [rsp+38h] [rbp-61h] BYREF
  __int64 v17; // [rsp+40h] [rbp-59h] BYREF
  char v18; // [rsp+48h] [rbp-51h]
  _OWORD v19[5]; // [rsp+50h] [rbp-49h] BYREF
  _OWORD v20[3]; // [rsp+A0h] [rbp+7h] BYREF
  _OWORD v21[2]; // [rsp+D0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  LPVOID pv; // [rsp+118h] [rbp+7Fh] BYREF

  if ( a2 )
  {
    v4 = -2147483637;
    v5 = 51;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
      (const char *)v4,
      v13);
    return v4;
  }
  if ( !a3 )
  {
    v4 = -2147467261;
    v5 = 52;
    goto LABEL_3;
  }
  memset(v19, 0, 76);
  pv = 0;
  *(_QWORD *)v15 = 0;
  v20[1] = v19[1];
  p_pv = &pv;
  v6 = *((_DWORD *)this + 16);
  v20[0] = v19[0];
  v21[0] = v19[3];
  *(_OWORD *)((char *)v21 + 12) = 0;
  v17 = 0;
  v18 = 1;
  v20[2] = v19[2];
  v7 = CGuestXvmAudioObject::SendAndValidateResponse<XvmFormatEnumeratorGetFormat>(
         (int)this + 16,
         v6,
         (unsigned int)v20,
         (unsigned int)&v17,
         (__int64)v15);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v7 >= 0 )
  {
    v10 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(0x12u);
    v11 = *(_QWORD *)v15;
    *a3 = v10;
    *(_OWORD *)&v10->wFormatTag = *(_OWORD *)(v11 + 4);
    v10->cbSize = *(_WORD *)(v11 + 20);
    v12 = pv;
    v4 = *((_DWORD *)pv + 1);
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    return v4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudioclient.cpp",
    (const char *)(unsigned int)v7,
    v14);
  v8 = pv;
  pv = 0;
  if ( v8 )
    CoTaskMemFree(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180100eb0  mov     [rsp-8+arg_0], rbx
0x180100eb5  mov     [rsp-8+arg_8], rdi
0x180100eba  push    rbp
0x180100ebb  lea     rbp, [rsp-57h]
0x180100ec0  sub     rsp, 0F0h
0x180100ec7  mov     rbx, r8
0x180100eca  mov     rax, rcx
0x180100ecd  test    edx, edx
0x180100ecf  jz      short loc_180100EF3
0x180100ed1  mov     ebx, 8000000Bh
0x180100ed6  mov     edx, 33h ; '3'; void *
0x180100edb  mov     rcx, [rbp+5Fh]; this
0x180100edf  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x180100ee6  mov     r9d, ebx; char *
0x180100ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100eee  jmp     loc_180101001
0x180100ef3  test    rbx, rbx
0x180100ef6  jnz     short loc_180100F04
0x180100ef8  mov     ebx, 80004003h
0x180100efd  mov     edx, 34h ; '4'
0x180100f02  jmp     short loc_180100EDB
0x180100f04  xor     ecx, ecx
0x180100f06  mov     dword ptr [rbp+57h+var_A0], 0
0x180100f0d  xorps   xmm0, xmm0
0x180100f10  mov     [rbp+57h+var_7C], rcx
0x180100f14  movups  [rbp+57h+var_A0+4], xmm0
0x180100f18  mov     [rbp+57h+pv], rcx
0x180100f1c  lea     rdx, [rbp+57h+var_C0]
0x180100f20  movups  [rbp+57h+var_8C], xmm0
0x180100f24  lea     r9, [rbp+57h+var_B0]
0x180100f28  mov     qword ptr [rbp+57h+var_C0], rcx
0x180100f2c  movaps  xmm1, xmmword ptr [rbp-39h]
0x180100f30  lea     rcx, [rbp+57h+pv]
0x180100f34  movaps  xmm0, [rbp+57h+var_A0]
0x180100f38  lea     r8, [rbp+57h+var_50]
0x180100f3c  xorps   xmm2, xmm2
0x180100f3f  movaps  [rbp+57h+var_40], xmm1
0x180100f43  movups  [rbp+57h+var_74], xmm2
0x180100f47  mov     [rbp+57h+var_B8], rcx
0x180100f4b  lea     rcx, [rax+10h]
0x180100f4f  movups  [rbp+57h+var_64], xmm2
0x180100f53  mov     qword ptr [rsp+0F0h+var_D0], rdx; int
0x180100f58  movaps  xmm1, [rbp+57h+var_74+4]
0x180100f5c  mov     edx, [rax+40h]
0x180100f5f  movaps  [rbp+57h+var_50], xmm0
0x180100f63  movaps  xmm0, [rbp+57h+var_8C+0Ch]
0x180100f67  movaps  xmmword ptr [rbp+57h+var_20], xmm1
0x180100f6b  movups  xmmword ptr [rbp+57h+var_20+0Ch], xmm2
0x180100f6f  mov     [rbp+57h+var_B0], 0
0x180100f77  mov     [rbp+57h+var_A8], 1
0x180100f7b  movaps  [rbp+57h+var_30], xmm0
0x180100f7f  call    ??$SendAndValidateResponse@UXvmFormatEnumeratorGetFormat@@@CGuestXvmAudioObject@@QEAAJIUXvmFormatEnumeratorGetFormat@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmFormatEnumeratorGetFormat>(uint,XvmFormatEnumeratorGetFormat,XvmMessage * *,XvmFormatEnumeratorGetFormat * *)
0x180100f84  lea     rcx, [rbp+57h+var_B8]
0x180100f88  mov     edi, eax
0x180100f8a  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180100f8f  test    edi, edi
0x180100f91  jns     short loc_180100FC6
0x180100f93  mov     rcx, [rbp+5Fh]; this
0x180100f97  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\client\\spatialaudio"...
0x180100f9e  mov     r9d, edi; char *
0x180100fa1  mov     edx, 3Ah ; ':'; void *
0x180100fa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100fab  mov     rcx, [rbp+57h+pv]; pv
0x180100faf  mov     [rbp+57h+pv], 0
0x180100fb7  test    rcx, rcx
0x180100fba  jz      short loc_180100FC2
0x180100fbc  call    cs:__imp_CoTaskMemFree
0x180100fc2  mov     eax, edi
0x180100fc4  jmp     short loc_180101003
0x180100fc6  mov     ecx, 12h; cb
0x180100fcb  call    cs:__imp_CoTaskMemAlloc
0x180100fd1  mov     rcx, qword ptr [rbp+57h+var_C0]
0x180100fd5  mov     [rbx], rax
0x180100fd8  movups  xmm0, xmmword ptr [rcx+4]
0x180100fdc  movups  xmmword ptr [rax], xmm0
0x180100fdf  movzx   ecx, word ptr [rcx+14h]
0x180100fe3  mov     [rax+10h], cx
0x180100fe7  mov     rcx, [rbp+57h+pv]; pv
0x180100feb  mov     ebx, [rcx+4]
0x180100fee  mov     [rbp+57h+pv], 0
0x180100ff6  test    rcx, rcx
0x180100ff9  jz      short loc_180101001
0x180100ffb  call    cs:__imp_CoTaskMemFree
0x180101001  mov     eax, ebx
0x180101003  lea     r11, [rsp+0F0h+var_s0]
0x18010100b  mov     rbx, [r11+10h]
0x18010100f  mov     rdi, [r11+18h]
0x180101013  mov     rsp, r11
0x180101016  pop     rbp
0x180101017  retn
```
