# XcGetNodeXml(IXMLDOMNode *,ushort * *)

- ea: `0x180012e8c`
- end: `0x180012fda`
- name: `?XcGetNodeXml@@YAKPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `334`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012fe0`

## callees

- `0x180012e8c`
- `0x1800133f8`
- `0x180013458`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180012fbf`
- `OLEAUT32!__imp_SysStringLen` at `0x180012ef0`
- `OLEAUT32!__imp_SysStringLen` at `0x180012ef0`

## pseudocode

```c
__int64 __fastcall XcGetNodeXml(struct IXMLDOMNode *a1, unsigned __int16 **a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v4; // eax
  DWORD LastError; // ebx
  unsigned __int16 *v6; // rdi
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  BSTR v9; // rcx
  __int64 v10; // rax
  unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rcx
  BSTR pbstr; // [rsp+40h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  pbstr = 0;
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_xml)(a1, &pbstr);
  LastError = v4;
  if ( v4 < 0 )
  {
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v4;
    if ( LastError )
      goto LABEL_28;
  }
  else
  {
    LastError = 0;
  }
  if ( !pbstr )
  {
    v6 = 0;
LABEL_24:
    *a2 = v6;
    goto LABEL_25;
  }
  v7 = SysStringLen(pbstr) + 1;
  v8 = (unsigned __int16 *)Xc_Process_user_allocate(2 * v7);
  v6 = v8;
  if ( v8 )
  {
    if ( v7 )
    {
      if ( v7 <= 0x7FFFFFFF )
      {
        v9 = pbstr;
        v10 = 2147483646;
        v11 = v6;
        do
        {
          if ( !v10 )
            break;
          if ( !*v9 )
            break;
          *v11++ = *v9++;
          --v10;
          --v7;
        }
        while ( v7 );
        v12 = v11 - 1;
        LastError = v7 == 0 ? 0x8007007A : 0;
        if ( v7 )
          v12 = v11;
        *v12 = 0;
        if ( v7 )
        {
          LastError = 0;
          goto LABEL_24;
        }
      }
      else
      {
        LOWORD(LastError) = 87;
        *v8 = 0;
      }
    }
    else
    {
      LOWORD(LastError) = 87;
    }
    LastError = (unsigned __int16)LastError;
    if ( (_WORD)LastError )
    {
LABEL_27:
      Xc_Process_user_free(v6);
      goto LABEL_28;
    }
    goto LABEL_24;
  }
  LastError = GetLastError();
LABEL_25:
  if ( LastError && v6 )
    goto LABEL_27;
LABEL_28:
  SysFreeString(pbstr);
  return LastError;
}

```

## disassembly

```asm
0x180012e8c  mov     r11, rsp
0x180012e8f  mov     [r11+10h], rbx
0x180012e93  mov     [r11+18h], rbp
0x180012e97  push    rsi
0x180012e98  push    rdi
0x180012e99  push    r14
0x180012e9b  sub     rsp, 20h
0x180012e9f  mov     rax, [rcx]
0x180012ea2  mov     r14, rdx
0x180012ea5  xor     ebp, ebp
0x180012ea7  lea     rdx, [r11+8]
0x180012eab  mov     [r11+8], rbp
0x180012eaf  mov     rax, [rax+110h]
0x180012eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ebb  mov     ebx, eax
0x180012ebd  test    eax, eax
0x180012ebf  js      short loc_180012EC5
0x180012ec1  mov     ebx, ebp
0x180012ec3  jmp     short loc_180012EDC
0x180012ec5  and     eax, 1FFF0000h
0x180012eca  cmp     eax, 70000h
0x180012ecf  jnz     short loc_180012ED4
0x180012ed1  movzx   ebx, bx
0x180012ed4  test    ebx, ebx
0x180012ed6  jnz     loc_180012FBA
0x180012edc  cmp     [rsp+38h+pbstr], rbp
0x180012ee1  jnz     short loc_180012EEB
0x180012ee3  mov     rdi, rbp
0x180012ee6  jmp     loc_180012FA6
0x180012eeb  mov     rcx, [rsp+38h+pbstr]; pbstr
0x180012ef0  call    cs:__imp_SysStringLen
0x180012ef6  inc     eax
0x180012ef8  mov     esi, eax
0x180012efa  lea     rcx, [rax+rax]; dwBytes
0x180012efe  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180012f03  mov     rdi, rax
0x180012f06  test    rax, rax
0x180012f09  jnz     short loc_180012F18
0x180012f0b  call    cs:__imp_GetLastError
0x180012f11  mov     ebx, eax
0x180012f13  jmp     loc_180012FA9
0x180012f18  test    rsi, rsi
0x180012f1b  jz      short loc_180012F92
0x180012f1d  cmp     rsi, 7FFFFFFFh
0x180012f24  jbe     short loc_180012F2D
0x180012f26  mov     ebx, 80070057h
0x180012f2b  jmp     short loc_180012F9C
0x180012f2d  mov     rcx, [rsp+38h+pbstr]
0x180012f32  mov     eax, 7FFFFFFEh
0x180012f37  mov     rdx, rdi
0x180012f3a  test    rax, rax
0x180012f3d  jz      short loc_180012F5E
0x180012f3f  movzx   r8d, word ptr [rcx]
0x180012f43  test    r8w, r8w
0x180012f47  jz      short loc_180012F5E
0x180012f49  mov     [rdx], r8w
0x180012f4d  add     rcx, 2
0x180012f51  add     rdx, 2
0x180012f55  dec     rax
0x180012f58  sub     rsi, 1
0x180012f5c  jnz     short loc_180012F3A
0x180012f5e  mov     rax, rsi
0x180012f61  lea     rcx, [rdx-2]
0x180012f65  neg     rax
0x180012f68  sbb     ebx, ebx
0x180012f6a  not     ebx
0x180012f6c  and     ebx, 8007007Ah
0x180012f72  test    rsi, rsi
0x180012f75  cmovnz  rcx, rdx
0x180012f79  mov     [rcx], bp
0x180012f7c  jz      short loc_180012F82
0x180012f7e  mov     ebx, ebp
0x180012f80  jmp     short loc_180012FA6
0x180012f82  mov     eax, ebx
0x180012f84  and     eax, 1FFF0000h
0x180012f89  cmp     eax, 70000h
0x180012f8e  jz      short loc_180012F9F
0x180012f90  jmp     short loc_180012FA2
0x180012f92  mov     ebx, 80070057h
0x180012f97  test    rsi, rsi
0x180012f9a  jz      short loc_180012F9F
0x180012f9c  mov     [rax], bp
0x180012f9f  movzx   ebx, bx
0x180012fa2  test    ebx, ebx
0x180012fa4  jnz     short loc_180012FB2
0x180012fa6  mov     [r14], rdi
0x180012fa9  test    ebx, ebx
0x180012fab  jz      short loc_180012FBA
0x180012fad  test    rdi, rdi
0x180012fb0  jz      short loc_180012FBA
0x180012fb2  mov     rcx, rdi; lpMem
0x180012fb5  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x180012fba  mov     rcx, [rsp+38h+pbstr]; bstrString
0x180012fbf  call    cs:__imp_SysFreeString
0x180012fc5  mov     rbp, [rsp+38h+arg_10]
0x180012fca  mov     eax, ebx
0x180012fcc  mov     rbx, [rsp+38h+arg_8]
0x180012fd1  add     rsp, 20h
0x180012fd5  pop     r14
0x180012fd7  pop     rdi
0x180012fd8  pop     rsi
0x180012fd9  retn
```
