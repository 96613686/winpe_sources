# BfspCleanupDebuggerSettings

- ea: `0x140004a60`
- end: `0x140004e17`
- name: `BfspCleanupDebuggerSettings`
- size: `951`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x140003d30`
- `0x140004080`

## callees

- `0x140004a60`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x140018890`
- `0x140019990`

## string_xrefs

- `0x140004e01`: `Failed to delete debugger settings element %08x. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCleanupDebuggerSettings(__int64 a1)
{
  int v2; // eax
  __int64 v3; // r8
  HANDLE v4; // rbp
  int ElementDataWithFlags; // edi
  __int64 v6; // r8
  __int64 v7; // r8
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // r8
  bool v25; // zf
  int v26; // eax
  __int64 v27; // r8
  int v28; // eax
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // r8
  int v34; // eax
  __int64 v35; // r8
  int v36; // eax
  __int64 v37; // r8
  int v38; // eax
  int v39; // eax
  __int64 v40; // r8
  int v41; // eax
  __int64 v42; // r8
  int v43; // eax
  __int64 v44; // r8
  int v45; // eax
  int v46; // eax
  int v48; // eax
  HANDLE Handle; // [rsp+58h] [rbp+10h] BYREF
  __int64 v50; // [rsp+60h] [rbp+18h] BYREF

  v50 = 0;
  BfspLogMessage(2, L"Cleaning up debugger settings.");
  Handle = 0;
  v2 = BcdOpenObject(a1, &GUID_DEBUGGER_SETTINGS_GROUP, &Handle);
  v4 = Handle;
  ElementDataWithFlags = v2;
  if ( v2 >= 0 )
  {
    LOBYTE(v3) = 1;
    BiDeleteElement(Handle, 369098763, v3);
    LODWORD(Handle) = 8;
    ElementDataWithFlags = BcdGetElementDataWithFlags((__int64)v4, 0x15000011u, v6, (__int64)&v50, &Handle);
    if ( ElementDataWithFlags >= 0 )
    {
      LOBYTE(v7) = 1;
      if ( v50 )
      {
        v8 = 352321555;
        if ( v50 != 1 )
        {
          if ( v50 != 2 )
          {
            if ( v50 != 3 )
            {
              v9 = BiDeleteElement(v4, 352321555, v7);
              ElementDataWithFlags = v9;
              if ( v9 >= 0 || v9 == -1073741275 )
              {
                v8 = 352321556;
                LOBYTE(v10) = 1;
                v11 = BiDeleteElement(v4, 352321556, v10);
                ElementDataWithFlags = v11;
                if ( v11 >= 0 || v11 == -1073741275 )
                {
                  v8 = 301989910;
                  LOBYTE(v12) = 1;
                  v13 = BiDeleteElement(v4, 301989910, v12);
                  ElementDataWithFlags = v13;
                  if ( v13 >= 0 || v13 == -1073741275 )
                  {
                    v8 = 352321557;
                    LOBYTE(v14) = 1;
                    v15 = BiDeleteElement(v4, 352321557, v14);
                    ElementDataWithFlags = v15;
                    if ( v15 >= 0 || v15 == -1073741275 )
                    {
                      v8 = 352321562;
                      LOBYTE(v16) = 1;
                      v17 = BiDeleteElement(v4, 352321562, v16);
                      ElementDataWithFlags = v17;
                      if ( v17 >= 0 || v17 == -1073741275 )
                      {
                        v8 = 352321563;
                        LOBYTE(v18) = 1;
                        v19 = BiDeleteElement(v4, 352321563, v18);
                        ElementDataWithFlags = v19;
                        if ( v19 >= 0 || v19 == -1073741275 )
                        {
                          v8 = 369098780;
                          LOBYTE(v20) = 1;
                          v21 = BiDeleteElement(v4, 369098780, v20);
                          ElementDataWithFlags = v21;
                          if ( v21 >= 0 || v21 == -1073741275 )
                          {
                            v8 = 301989917;
                            LOBYTE(v22) = 1;
                            v23 = BiDeleteElement(v4, 301989917, v22);
                            ElementDataWithFlags = v23;
                            if ( v23 >= 0 || v23 == -1073741275 )
                            {
                              v8 = 301989913;
                              LOBYTE(v24) = 1;
                              ElementDataWithFlags = BiDeleteElement(v4, 301989913, v24);
                              if ( (int)(ElementDataWithFlags + 0x80000000) >= 0 )
                              {
                                v25 = ElementDataWithFlags == -1073741275;
                                goto LABEL_54;
                              }
                              goto LABEL_55;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
LABEL_62:
              BfspLogMessage(
                4,
                L"Failed to delete debugger settings element %08x. Status = [%x]",
                v8,
                (unsigned int)ElementDataWithFlags);
              goto LABEL_56;
            }
            v26 = BiDeleteElement(v4, 352321555, v7);
            ElementDataWithFlags = v26;
            if ( v26 < 0 && v26 != -1073741275 )
              goto LABEL_62;
            v8 = 352321556;
            LOBYTE(v27) = 1;
            v28 = BiDeleteElement(v4, 352321556, v27);
            ElementDataWithFlags = v28;
            if ( v28 < 0 && v28 != -1073741275 )
              goto LABEL_62;
            v8 = 352321557;
            LOBYTE(v29) = 1;
            v30 = BiDeleteElement(v4, 352321557, v29);
            ElementDataWithFlags = v30;
            if ( v30 < 0 && v30 != -1073741275 )
              goto LABEL_62;
            v8 = 301989910;
LABEL_52:
            LOBYTE(v31) = 1;
            v46 = BiDeleteElement(v4, v8, v31);
            ElementDataWithFlags = v46;
            if ( v46 < 0 )
            {
              v25 = v46 == -1073741275;
LABEL_54:
              if ( v25 )
                goto LABEL_55;
              goto LABEL_62;
            }
LABEL_55:
            ElementDataWithFlags = 0;
            goto LABEL_56;
          }
          v32 = BiDeleteElement(v4, 352321555, v7);
          ElementDataWithFlags = v32;
          if ( v32 < 0 && v32 != -1073741275 )
            goto LABEL_62;
          v8 = 352321556;
          LOBYTE(v33) = 1;
          v34 = BiDeleteElement(v4, 352321556, v33);
          ElementDataWithFlags = v34;
          if ( v34 < 0 && v34 != -1073741275 )
            goto LABEL_62;
          v8 = 352321557;
LABEL_43:
          LOBYTE(v35) = 1;
          v39 = BiDeleteElement(v4, v8, v35);
          ElementDataWithFlags = v39;
          if ( v39 < 0 && v39 != -1073741275 )
            goto LABEL_62;
          v8 = 352321562;
          LOBYTE(v40) = 1;
          v41 = BiDeleteElement(v4, 352321562, v40);
          ElementDataWithFlags = v41;
          if ( v41 < 0 && v41 != -1073741275 )
            goto LABEL_62;
          v8 = 352321563;
          LOBYTE(v42) = 1;
          v43 = BiDeleteElement(v4, 352321563, v42);
          ElementDataWithFlags = v43;
          if ( v43 < 0 && v43 != -1073741275 )
            goto LABEL_62;
          v8 = 369098780;
          LOBYTE(v44) = 1;
          v45 = BiDeleteElement(v4, 369098780, v44);
          ElementDataWithFlags = v45;
          if ( v45 < 0 && v45 != -1073741275 )
            goto LABEL_62;
          v8 = 301989917;
          goto LABEL_52;
        }
        v36 = BiDeleteElement(v4, 352321555, v7);
        ElementDataWithFlags = v36;
        if ( v36 < 0 && v36 != -1073741275 )
          goto LABEL_62;
        v8 = 352321556;
      }
      else
      {
        v8 = 352321557;
        v48 = BiDeleteElement(v4, 352321557, v7);
        ElementDataWithFlags = v48;
        if ( v48 < 0 && v48 != -1073741275 )
          goto LABEL_62;
        v8 = 301989913;
      }
      LOBYTE(v37) = 1;
      v38 = BiDeleteElement(v4, v8, v37);
      ElementDataWithFlags = v38;
      if ( v38 < 0 && v38 != -1073741275 )
        goto LABEL_62;
      v8 = 301989910;
      goto LABEL_43;
    }
  }
LABEL_56:
  if ( v4 )
    BcdCloseObject(v4);
  return (unsigned int)ElementDataWithFlags;
}

```

## disassembly

```asm
0x140004a60  mov     [rsp+arg_0], rbx
0x140004a65  push    rbp
0x140004a66  push    rsi
0x140004a67  push    rdi
0x140004a68  sub     rsp, 30h
0x140004a6c  mov     rbx, rcx
0x140004a6f  mov     [rsp+48h+arg_10], 0
0x140004a78  mov     ecx, 2
0x140004a7d  lea     rdx, aCleaningUpDebu; "Cleaning up debugger settings."
0x140004a84  call    BfspLogMessage
0x140004a89  lea     r8, [rsp+48h+Handle]
0x140004a8e  mov     [rsp+48h+Handle], 0
0x140004a97  lea     rdx, GUID_DEBUGGER_SETTINGS_GROUP
0x140004a9e  mov     rcx, rbx
0x140004aa1  call    BcdOpenObject
0x140004aa6  mov     rbp, [rsp+48h+Handle]
0x140004aab  mov     edi, eax
0x140004aad  test    eax, eax
0x140004aaf  js      loc_140004DBD
0x140004ab5  mov     r8b, 1
0x140004ab8  mov     edx, 1600000Bh
0x140004abd  mov     rcx, rbp
0x140004ac0  call    BiDeleteElement
0x140004ac5  lea     rax, [rsp+48h+Handle]
0x140004aca  mov     dword ptr [rsp+48h+Handle], 8
0x140004ad2  lea     r9, [rsp+48h+arg_10]
0x140004ad7  mov     [rsp+48h+var_28], rax
0x140004adc  mov     edx, 15000011h
0x140004ae1  mov     rcx, rbp
0x140004ae4  call    BcdGetElementDataWithFlags
0x140004ae9  mov     edi, eax
0x140004aeb  test    eax, eax
0x140004aed  js      loc_140004DBD
0x140004af3  mov     rax, [rsp+48h+arg_10]
0x140004af8  mov     r8b, 1
0x140004afb  mov     rcx, rbp
0x140004afe  test    rax, rax
0x140004b01  jz      loc_140004DD9
0x140004b07  mov     ebx, 15000013h
0x140004b0c  mov     edx, ebx
0x140004b0e  sub     rax, 1
0x140004b12  jz      loc_140004CEF
0x140004b18  sub     rax, 1
0x140004b1c  jz      loc_140004CB0
0x140004b22  cmp     rax, 1
0x140004b26  jz      loc_140004C4E
0x140004b2c  call    BiDeleteElement
0x140004b31  mov     edi, eax
0x140004b33  mov     esi, 0C0000225h
0x140004b38  test    eax, eax
0x140004b3a  jns     short loc_140004B44
0x140004b3c  cmp     eax, esi
0x140004b3e  jnz     loc_140004DFE
0x140004b44  mov     ebx, 15000014h
0x140004b49  mov     r8b, 1
0x140004b4c  mov     edx, ebx
0x140004b4e  mov     rcx, rbp
0x140004b51  call    BiDeleteElement
0x140004b56  mov     edi, eax
0x140004b58  test    eax, eax
0x140004b5a  jns     short loc_140004B64
0x140004b5c  cmp     eax, esi
0x140004b5e  jnz     loc_140004DFE
0x140004b64  mov     ebx, 12000016h
0x140004b69  mov     r8b, 1
0x140004b6c  mov     edx, ebx
0x140004b6e  mov     rcx, rbp
0x140004b71  call    BiDeleteElement
0x140004b76  mov     edi, eax
0x140004b78  test    eax, eax
0x140004b7a  jns     short loc_140004B84
0x140004b7c  cmp     eax, esi
0x140004b7e  jnz     loc_140004DFE
0x140004b84  mov     ebx, 15000015h
0x140004b89  mov     r8b, 1
0x140004b8c  mov     edx, ebx
0x140004b8e  mov     rcx, rbp
0x140004b91  call    BiDeleteElement
0x140004b96  mov     edi, eax
0x140004b98  test    eax, eax
0x140004b9a  jns     short loc_140004BA4
0x140004b9c  cmp     eax, esi
0x140004b9e  jnz     loc_140004DFE
0x140004ba4  mov     ebx, 1500001Ah
0x140004ba9  mov     r8b, 1
0x140004bac  mov     edx, ebx
0x140004bae  mov     rcx, rbp
0x140004bb1  call    BiDeleteElement
0x140004bb6  mov     edi, eax
0x140004bb8  test    eax, eax
0x140004bba  jns     short loc_140004BC4
0x140004bbc  cmp     eax, esi
0x140004bbe  jnz     loc_140004DFE
0x140004bc4  mov     ebx, 1500001Bh
0x140004bc9  mov     r8b, 1
0x140004bcc  mov     edx, ebx
0x140004bce  mov     rcx, rbp
0x140004bd1  call    BiDeleteElement
0x140004bd6  mov     edi, eax
0x140004bd8  test    eax, eax
0x140004bda  jns     short loc_140004BE4
0x140004bdc  cmp     eax, esi
0x140004bde  jnz     loc_140004DFE
0x140004be4  mov     ebx, 1600001Ch
0x140004be9  mov     r8b, 1
0x140004bec  mov     edx, ebx
0x140004bee  mov     rcx, rbp
0x140004bf1  call    BiDeleteElement
0x140004bf6  mov     edi, eax
0x140004bf8  test    eax, eax
0x140004bfa  jns     short loc_140004C04
0x140004bfc  cmp     eax, esi
0x140004bfe  jnz     loc_140004DFE
0x140004c04  mov     ebx, 1200001Dh
0x140004c09  mov     r8b, 1
0x140004c0c  mov     edx, ebx
0x140004c0e  mov     rcx, rbp
0x140004c11  call    BiDeleteElement
0x140004c16  mov     edi, eax
0x140004c18  test    eax, eax
0x140004c1a  jns     short loc_140004C24
0x140004c1c  cmp     eax, esi
0x140004c1e  jnz     loc_140004DFE
0x140004c24  mov     ebx, 12000019h
0x140004c29  mov     r8b, 1
0x140004c2c  mov     edx, ebx
0x140004c2e  mov     rcx, rbp
0x140004c31  call    BiDeleteElement
0x140004c36  mov     ecx, 80000000h
0x140004c3b  mov     edi, eax
0x140004c3d  add     eax, ecx
0x140004c3f  test    ecx, eax
0x140004c41  jnz     loc_140004DBB
0x140004c47  cmp     edi, esi
0x140004c49  jmp     loc_140004DB9
0x140004c4e  call    BiDeleteElement
0x140004c53  mov     edi, eax
0x140004c55  mov     esi, 0C0000225h
0x140004c5a  test    eax, eax
0x140004c5c  jns     short loc_140004C66
0x140004c5e  cmp     eax, esi
0x140004c60  jnz     loc_140004DFE
0x140004c66  mov     ebx, 15000014h
0x140004c6b  mov     r8b, 1
0x140004c6e  mov     edx, ebx
0x140004c70  mov     rcx, rbp
0x140004c73  call    BiDeleteElement
0x140004c78  mov     edi, eax
0x140004c7a  test    eax, eax
0x140004c7c  jns     short loc_140004C86
0x140004c7e  cmp     eax, esi
0x140004c80  jnz     loc_140004DFE
0x140004c86  mov     ebx, 15000015h
0x140004c8b  mov     r8b, 1
0x140004c8e  mov     edx, ebx
0x140004c90  mov     rcx, rbp
0x140004c93  call    BiDeleteElement
0x140004c98  mov     edi, eax
0x140004c9a  test    eax, eax
0x140004c9c  jns     short loc_140004CA6
0x140004c9e  cmp     eax, esi
0x140004ca0  jnz     loc_140004DFE
0x140004ca6  mov     ebx, 12000016h
0x140004cab  jmp     loc_140004DA4
0x140004cb0  call    BiDeleteElement
0x140004cb5  mov     edi, eax
0x140004cb7  mov     esi, 0C0000225h
0x140004cbc  test    eax, eax
0x140004cbe  jns     short loc_140004CC8
0x140004cc0  cmp     eax, esi
0x140004cc2  jnz     loc_140004DFE
0x140004cc8  mov     ebx, 15000014h
0x140004ccd  mov     r8b, 1
0x140004cd0  mov     edx, ebx
0x140004cd2  mov     rcx, rbp
0x140004cd5  call    BiDeleteElement
0x140004cda  mov     edi, eax
0x140004cdc  test    eax, eax
0x140004cde  jns     short loc_140004CE8
0x140004ce0  cmp     eax, esi
0x140004ce2  jnz     loc_140004DFE
0x140004ce8  mov     ebx, 15000015h
0x140004ced  jmp     short loc_140004D2C
0x140004cef  call    BiDeleteElement
0x140004cf4  mov     edi, eax
0x140004cf6  mov     esi, 0C0000225h
0x140004cfb  test    eax, eax
0x140004cfd  jns     short loc_140004D07
0x140004cff  cmp     eax, esi
0x140004d01  jnz     loc_140004DFE
0x140004d07  mov     ebx, 15000014h
0x140004d0c  mov     r8b, 1
0x140004d0f  mov     edx, ebx
0x140004d11  mov     rcx, rbp
0x140004d14  call    BiDeleteElement
0x140004d19  mov     edi, eax
0x140004d1b  test    eax, eax
0x140004d1d  jns     short loc_140004D27
0x140004d1f  cmp     eax, esi
0x140004d21  jnz     loc_140004DFE
0x140004d27  mov     ebx, 12000016h
0x140004d2c  mov     r8b, 1
0x140004d2f  mov     edx, ebx
0x140004d31  mov     rcx, rbp
0x140004d34  call    BiDeleteElement
0x140004d39  mov     edi, eax
0x140004d3b  test    eax, eax
0x140004d3d  jns     short loc_140004D47
0x140004d3f  cmp     eax, esi
0x140004d41  jnz     loc_140004DFE
0x140004d47  mov     ebx, 1500001Ah
0x140004d4c  mov     r8b, 1
0x140004d4f  mov     edx, ebx
0x140004d51  mov     rcx, rbp
0x140004d54  call    BiDeleteElement
0x140004d59  mov     edi, eax
0x140004d5b  test    eax, eax
0x140004d5d  jns     short loc_140004D67
0x140004d5f  cmp     eax, esi
0x140004d61  jnz     loc_140004DFE
0x140004d67  mov     ebx, 1500001Bh
0x140004d6c  mov     r8b, 1
0x140004d6f  mov     edx, ebx
0x140004d71  mov     rcx, rbp
0x140004d74  call    BiDeleteElement
0x140004d79  mov     edi, eax
0x140004d7b  test    eax, eax
0x140004d7d  jns     short loc_140004D83
0x140004d7f  cmp     eax, esi
0x140004d81  jnz     short loc_140004DFE
0x140004d83  mov     ebx, 1600001Ch
0x140004d88  mov     r8b, 1
0x140004d8b  mov     edx, ebx
0x140004d8d  mov     rcx, rbp
0x140004d90  call    BiDeleteElement
0x140004d95  mov     edi, eax
0x140004d97  test    eax, eax
0x140004d99  jns     short loc_140004D9F
0x140004d9b  cmp     eax, esi
0x140004d9d  jnz     short loc_140004DFE
0x140004d9f  mov     ebx, 1200001Dh
0x140004da4  mov     r8b, 1
0x140004da7  mov     edx, ebx
0x140004da9  mov     rcx, rbp
0x140004dac  call    BiDeleteElement
0x140004db1  mov     edi, eax
0x140004db3  test    eax, eax
0x140004db5  jns     short loc_140004DBB
0x140004db7  cmp     eax, esi
0x140004db9  jnz     short loc_140004DFE
0x140004dbb  xor     edi, edi
0x140004dbd  test    rbp, rbp
0x140004dc0  jz      short loc_140004DCA
0x140004dc2  mov     rcx, rbp; Handle
0x140004dc5  call    BcdCloseObject
0x140004dca  mov     rbx, [rsp+48h+arg_0]
0x140004dcf  mov     eax, edi
0x140004dd1  add     rsp, 30h
0x140004dd5  pop     rdi
0x140004dd6  pop     rsi
0x140004dd7  pop     rbp
0x140004dd8  retn
0x140004dd9  mov     ebx, 15000015h
0x140004dde  mov     edx, ebx
0x140004de0  call    BiDeleteElement
0x140004de5  mov     edi, eax
0x140004de7  mov     esi, 0C0000225h
0x140004dec  test    eax, eax
0x140004dee  jns     short loc_140004DF4
0x140004df0  cmp     eax, esi
0x140004df2  jnz     short loc_140004DFE
0x140004df4  mov     ebx, 12000019h
0x140004df9  jmp     loc_140004D0C
0x140004dfe  mov     r9d, edi
0x140004e01  lea     rdx, aFailedToDelete_2; "Failed to delete debugger settings elem"...
0x140004e08  mov     r8d, ebx
0x140004e0b  mov     ecx, 4
0x140004e10  call    BfspLogMessage
0x140004e15  jmp     short loc_140004DBD
```
